# Guía para probar el Smart Contract de Compraventa


## 1️ Crear una cuenta en MetaMask

1. Abre [https://metamask.io/](https://metamask.io/) en tu navegador.
2. Haz clic en "**Download**" y luego instala la **extensión de MetaMask** en tu navegador.
3. Una vez instalada, haz clic en el ícono de MetaMask (zorro naranja) en la barra de extensiones.
4. Elige "**Crear una nueva billetera**".

## 2️ Conectarte a la red de pruebas Sepolia

1. Abre MetaMask.
2. En la parte superior donde dice "**Ethereum Mainnet**", haz clic y selecciona "**Sepolia Test Network**".  

## 3️ Conseguir ETH de prueba en Sepolia

1. Entra a un faucet de Sepolia como:
   - https://cloud.google.com/application/web3/faucet/ethereum/sepolia
   - https://sepolia-faucet.pk910.de
1. Pega tu dirección de MetaMask (empieza por `0x...`) y solicita ETH gratis de prueba.
2. Espera unos minutos hasta recibir tus Sepolia ETH.

## 4️ Acceder a Remix IDE

1. Abre [https://remix.ethereum.org/](https://remix.ethereum.org/) en el navegador.

## 5️ Crear el contrato inteligente de compraventa

1. En Remix:
   - Haz clic en el ícono de archivos (a la izquierda).
   - Crea un nuevo archivo llamado: `Compraventa.sol`.
2. Copia y pega el código del archivo`Compraventa.sol` de github:

## 6 Compilar el contrato

1. Haz  click en el ícono de compilador en remix
2. Presiona compile  **Compile CompraVenta.sol**

## 7 Conectar Remix con MetaMask

1. Haz click en el ícono **Deploy & Run Transactions**
2. En **Environment**, selecciona connect Wallet.
3. Selecciona el icono de MetaMask.
4. Dale Permiso para que acepte.

## 8️ Desplegar el contrato en la red Sepolia

1. **Acceder a la sección "Deploy"** en Remix:
   - Busca el apartado **"Deploy & Run Transactions"**.
   - En la sección **"Deploy"**, encontrarás un campo para introducir un parámetro: el **precio en wei**.

2. **Establecer el precio en wei**:
   - El contrato `Compraventa` pide un precio como parámetro (en wei). Por ejemplo, si el precio que deseas es 0.01 ETH:
     - Convierte 0.01 ETH a wei: `0.01 * 10^18 = 10000000000000000 wei`.
     - Introduce `10000000000000000` en el campo de parámetros en Remix.

3. **Desplegar el contrato**:
   - Haz clic en el botón **"Deploy"**.
   - MetaMask se abrirá y te pedirá confirmar el **gasto de gas** para desplegar el contrato. Acepta la transacción.
   - **Espera unos segundos** mientras el contrato se despliega en la blockchain de Sepolia.

---

## 9️ Interactuar con el contrato

1. **Ver contrato desplegado**:
   - En Remix, después del despliegue, ve a la sección **"Deployed Contracts"**.
   - Allí encontrarás el contrato `Compraventa` desplegado y listo para interactuar.

2. **Consultar información**:
   - Haz clic en el método `obtenerInformacion()` para ver los detalles del contrato desplegado:
     - Dirección del vendedor.
     - Dirección del comprador (vacío si no se ha realizado la compra).
     - El precio del contrato en wei.
     - Estado del pago (si se ha realizado o no).

3. **Realizar la compra**:
   - Dirígete al método `comprar()`.
   - Asegúrate de que el **valor exacto** que introduces en Remix sea igual al precio del contrato en wei.
   - Haz clic en **"comprar()"** para realizar la compra.
   - MetaMask se abrirá para confirmar la transacción. Acepta y espera a que se complete.

4. **Verificar la compra**:
   - Una vez realizada la compra, puedes volver a hacer clic en `obtenerInformacion()` para verificar que:
     - La dirección del comprador se haya actualizado.
     - El estado de pago esté marcado como **true**.

---
