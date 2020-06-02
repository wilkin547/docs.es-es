---
title: 'Tutorial: Crear una aplicación criptográfica'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cryptography [NET Framework], example
- cryptography [NET Framework], cryptographic application example
- cryptography [NET Framework], application example
ms.assetid: abf48c11-1e72-431d-9562-39cf23e1a8ff
ms.openlocfilehash: 246028566c59e5c8a77b26a21729d3f143d38d07
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84289712"
---
# <a name="walkthrough-creating-a-cryptographic-application"></a>Tutorial: Crear una aplicación criptográfica
En este tutorial se muestra cómo cifrar y descifrar contenido. Los ejemplos de código están diseñados para una aplicación de Windows Forms. Esta aplicación no muestra escenarios del mundo real, como el uso de tarjetas inteligentes. En su lugar, muestra los aspectos básicos del cifrado y el descifrado.  
  
 En este tutorial se usan las siguientes directrices para el cifrado:  
  
- Use la clase <xref:System.Security.Cryptography.RijndaelManaged>, un algoritmo simétrico, para cifrar y descifrar datos mediante su <xref:System.Security.Cryptography.SymmetricAlgorithm.Key%2A> y <xref:System.Security.Cryptography.SymmetricAlgorithm.IV%2A> generados automáticamente.  
  
- Use el <xref:System.Security.Cryptography.RSACryptoServiceProvider>, un algoritmo asimétrico, para cifrar y descifrar la clave en los datos cifrados por <xref:System.Security.Cryptography.RijndaelManaged>. Los algoritmos asimétricos son útiles para pequeñas cantidades de datos, como las claves.  
  
    > [!NOTE]
    > Si desea proteger los datos en el equipo en lugar de intercambiar contenido cifrado con otras personas, considere la posibilidad de usar la clase <xref:System.Security.Cryptography.ProtectedData> o <xref:System.Security.Cryptography.ProtectedMemory>.  
  
 En la tabla siguiente se resumen las tareas criptográficas de este tema.  
  
|Tarea|Descripción|  
|----------|-----------------|  
|Crear una aplicación de Windows Forms|Enumera los controles necesarios para ejecutar la aplicación.|  
|Declarar objetos globales|Declara variables de ruta de acceso de cadena, los <xref:System.Security.Cryptography.CspParameters> y el <xref:System.Security.Cryptography.RSACryptoServiceProvider> para disponer del contexto global de la clase <xref:System.Windows.Forms.Form>.|  
|Crear una clave asimétrica|Crea un par de valores de claves pública y privada asimétricas y le asigna un nombre de contenedor de claves.|  
|Cifrar un archivo|Muestra un cuadro de diálogo para seleccionar un archivo para el cifrado y lo cifra.|  
|Descifrar un archivo|Muestra un cuadro de diálogo para seleccionar un archivo cifrado para el descifrado y lo descifra.|  
|Obtener una clave privada|Obtiene el par de claves completo con el nombre del contenedor de claves.|  
|Exportar una clave pública|Guarda la clave en un archivo XML únicamente con parámetros públicos.|  
|Importar una clave pública|Carga la clave desde un archivo XML en el contenedor de claves.|  
|Probar la aplicación|Enumera los procedimientos para probar esta aplicación.|  
  
## <a name="prerequisites"></a>Prerrequisitos  
 Necesitará los componentes siguientes para completar este tutorial:  
  
- Referencias a los espacios de nombres <xref:System.IO> y <xref:System.Security.Cryptography>.  
  
## <a name="creating-a-windows-forms-application"></a>Crear una aplicación de Windows Forms  
 La mayoría de los ejemplos de código de este tutorial están diseñados para actuar como controladores de eventos de los controles de botón. En la tabla siguiente se enumeran los controles necesarios para que la aplicación de ejemplo y los nombres necesarios coincidan con los ejemplos de código.  
  
|Control|Nombre|Propiedad de texto (según sea necesario)|  
|-------------|----------|---------------------------------|  
|<xref:System.Windows.Forms.Button>|`buttonEncryptFile`|Cifrar archivo|  
|<xref:System.Windows.Forms.Button>|`buttonDecryptFile`|Descifrar archivo|  
|<xref:System.Windows.Forms.Button>|`buttonCreateAsmKeys`|Crear claves|  
|<xref:System.Windows.Forms.Button>|`buttonExportPublicKey`|Exportar la clave pública|  
|<xref:System.Windows.Forms.Button>|`buttonImportPublicKey`|Importar la clave pública|  
|<xref:System.Windows.Forms.Button>|`buttonGetPrivateKey`|Obtener la clave privada|  
|<xref:System.Windows.Forms.Label>|`label1`|Clave no establecida|  
|<xref:System.Windows.Forms.OpenFileDialog>|`openFileDialog1`||  
|<xref:System.Windows.Forms.OpenFileDialog>|`openFileDialog2`||  
  
 Haga doble clic en los botones del Diseñador de Visual Studio para crear los controladores de eventos.  
  
## <a name="declaring-global-objects"></a>Declarar objetos globales  
 Agregue el siguiente código al constructor del formulario. Edite las variables de cadena para el entorno y las preferencias.  
  
 [!code-csharp[CryptoWalkThru#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#1)]
 [!code-vb[CryptoWalkThru#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#1)]  
  
## <a name="creating-an-asymmetric-key"></a>Crear una clave asimétrica  
 Esta tarea crea una clave asimétrica que cifra y descifra la clave <xref:System.Security.Cryptography.RijndaelManaged>. Esta clave se usó para cifrar el contenido y muestra el nombre del contenedor de claves en el control de etiqueta.  
  
 Agregue el siguiente código como controlador de eventos `Click` del botón `Create Keys` (`buttonCreateAsmKeys_Click`).  
  
 [!code-csharp[CryptoWalkThru#2](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#2)]
 [!code-vb[CryptoWalkThru#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#2)]  
  
## <a name="encrypting-a-file"></a>Cifrar un archivo  
 Esta tarea implica dos métodos: el método de control de eventos para el `Encrypt File` botón ( `buttonEncryptFile_Click` ) y el `EncryptFile` método. El primer método muestra un cuadro de diálogo para seleccionar un archivo y pasa el nombre del archivo al segundo método, que lleva a cabo el cifrado.  
  
 El contenido cifrado, la clave y el vector de inicialización (IV) se guardan en un <xref:System.IO.FileStream>, conocido como paquete de cifrado.  
  
 El método `EncryptFile` hace lo siguiente:  
  
1. Crea un algoritmo simétrico <xref:System.Security.Cryptography.RijndaelManaged> para cifrar el contenido.  
  
2. Crea un objeto <xref:System.Security.Cryptography.RSACryptoServiceProvider> para cifrar la clave <xref:System.Security.Cryptography.RijndaelManaged>.  
  
3. Usa un objeto <xref:System.Security.Cryptography.CryptoStream> para leer y cifrar el <xref:System.IO.FileStream> del archivo de código fuente, en bloques de bytes, en un objeto <xref:System.IO.FileStream> de destino para el archivo cifrado.  
  
4. Determina la longitud de la clave cifrada y del IV y crea matrices de bytes de sus valores de longitud.  
  
5. Escribe la clave, el IV y sus valores de longitud en el paquete cifrado.  
  
 El paquete de cifrado usa el siguiente formato:  
  
- Longitud de clave, bytes 0 - 3  
  
- Longitud del IV, bytes 4 - 7  
  
- Clave cifrada  
  
- IV  
  
- Texto cifrado  
  
 Puede usar la longitud de la clave y del IV para determinar los puntos iniciales y la longitud de todas las partes del paquete de cifrado, que posteriormente se puede usar para descifrar el archivo.  
  
 Agregue el siguiente código como controlador de eventos `Click` del botón `Encrypt File` (`buttonEncryptFile_Click`).  
  
 [!code-csharp[CryptoWalkThru#3](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#3)]
 [!code-vb[CryptoWalkThru#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#3)]  
  
 Agregue el siguiente método `EncryptFile` al formulario.  
  
 [!code-csharp[CryptoWalkThru#5](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#5)]
 [!code-vb[CryptoWalkThru#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#5)]  
  
## <a name="decrypting-a-file"></a>Descifrar un archivo  
 Esta tarea implica dos métodos: el método del controlador de eventos del botón `Decrypt File` (`buttonDecryptFile_Click`) y el método `DecryptFile`. El primer método muestra un cuadro de diálogo para seleccionar un archivo y pasa su nombre al segundo método, que lleva a cabo el descifrado.  
  
 El método `Decrypt` hace lo siguiente:  
  
1. Crea un algoritmo simétrico <xref:System.Security.Cryptography.RijndaelManaged> para descifrar el contenido.  
  
2. Lee los primeros ocho bytes del <xref:System.IO.FileStream> del paquete de cifrado en matrices de bytes para obtener la longitud de la clave cifrada y del IV.  
  
3. Extrae la clave y el IV del paquete de cifrado en matrices de bytes.  
  
4. Crea un objeto <xref:System.Security.Cryptography.RSACryptoServiceProvider> para descifrar la clave <xref:System.Security.Cryptography.RijndaelManaged>.  
  
5. Usa un objeto <xref:System.Security.Cryptography.CryptoStream> para leer y descifrar la sección de texto cifrado del paquete de cifrado <xref:System.IO.FileStream>, en bloques de bytes, en el objeto <xref:System.IO.FileStream> del archivo descifrado. Al finalizar, se habrá completado el descifrado.  
  
 Agregue el siguiente código como controlador de eventos `Click` del botón `Decrypt File`.  
  
 [!code-csharp[CryptoWalkThru#4](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#4)]
 [!code-vb[CryptoWalkThru#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#4)]  
  
 Agregue el siguiente método `DecryptFile` al formulario.  
  
 [!code-csharp[CryptoWalkThru#6](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#6)]
 [!code-vb[CryptoWalkThru#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#6)]  
  
## <a name="exporting-a-public-key"></a>Exportar una clave pública  
 Esta tarea guarda en un archivo la clave creada por el botón `Create Keys`. Solo exporta los parámetros públicos.  
  
 Esta tarea simula un escenario en que Alicia da a Roberto su clave pública para que pueda cifrar archivos por ella. Roberto y otras personas que tengan esa clave pública no podrán descifrarlos porque no tienen el par de claves completo con los parámetros privados.  
  
 Agregue el siguiente código como controlador de eventos `Click` del botón `Export Public Key` (`buttonExportPublicKey_Click`).  
  
 [!code-csharp[CryptoWalkThru#8](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#8)]
 [!code-vb[CryptoWalkThru#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#8)]  
  
## <a name="importing-a-public-key"></a>Importar una clave pública  
 Esta tarea carga la clave únicamente con parámetros públicos, tal como se creó con el botón `Export Public Key`, y la establece con el nombre del contenedor de claves.  
  
 Esta tarea simula un escenario en que Roberto carga la clave de Alicia que solo tiene parámetros públicos, de manera que pueda cifrar archivos por ella.  
  
 Agregue el siguiente código como controlador de eventos `Click` del botón `Import Public Key` (`buttonImportPublicKey_Click`).  
  
 [!code-csharp[CryptoWalkThru#9](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#9)]
 [!code-vb[CryptoWalkThru#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#9)]  
  
## <a name="getting-a-private-key"></a>Obtener una clave privada  
 Esta tarea establece el nombre del contenedor de claves con el nombre de la clave creada mediante el botón `Create Keys`. El contenedor de claves contendrá el par de claves completo con los parámetros privados.  
  
 Esta tarea simula un escenario en que Alicia usa su clave privada para descifrar archivos cifrados por Roberto.  
  
 Agregue el siguiente código como controlador de eventos `Click` del botón `Get Private Key` (`buttonGetPrivateKey_Click`).  
  
 [!code-csharp[CryptoWalkThru#7](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#7)]
 [!code-vb[CryptoWalkThru#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#7)]  
  
## <a name="testing-the-application"></a>Prueba de la aplicación  
 Después de haber compilado la aplicación, ejecute los siguientes escenarios de prueba.  
  
#### <a name="to-create-keys-encrypt-and-decrypt"></a>Para crear claves, cifrar y descifrar  
  
1. Haga clic en el botón `Create Keys`. La etiqueta muestra el nombre de la clave e indica que se trata de un par de claves completo.  
  
2. Haga clic en el botón `Export Public Key`. Tenga en cuenta que al exportar los parámetros de la clave pública no se cambia la clave actual.  
  
3. Haga clic en el botón `Encrypt File` y seleccione un archivo.  
  
4. Haga clic en el botón `Decrypt File` y seleccione el archivo que acaba de cifrar.  
  
5. Examine el archivo que acaba de descifrar.  
  
6. Cierre la aplicación y reiníciela para intentar recuperar los contenedores de claves persistentes en el siguiente escenario.  
  
#### <a name="to-encrypt-using-the-public-key"></a>Para cifrar con la clave pública  
  
1. Haga clic en el botón `Import Public Key`. La etiqueta muestra el nombre de la clave e indica que solo es pública.  
  
2. Haga clic en el botón `Encrypt File` y seleccione un archivo.  
  
3. Haga clic en el botón `Decrypt File` y seleccione el archivo que acaba de cifrar. Esto generará un error porque debe disponer de la clave privada para efectuar el descifrado.  
  
 En este escenario se muestra una situación en la que solo se dispone de la clave pública para cifrar un archivo para otra persona. Normalmente, esa persona debe proporcionarle únicamente la clave pública y conservar la clave privada para el descifrado.  
  
#### <a name="to-decrypt-using-the-private-key"></a>Para descifrar con la clave privada  
  
1. Haga clic en el botón `Get Private Key`. La etiqueta muestra el nombre de la clave e indica si se trata del par de claves completo.  
  
2. Haga clic en el botón `Decrypt File` y seleccione el archivo que acaba de cifrar. Esta acción se llevará a cabo correctamente porque dispone del par de claves completo para efectuar el descifrado.  
  
## <a name="see-also"></a>Consulte también

- [Servicios criptográficos](cryptographic-services.md)
