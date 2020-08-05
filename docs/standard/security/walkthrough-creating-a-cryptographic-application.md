---
title: 'Tutorial: Crear una aplicación criptográfica'
description: Recorra la creación de una aplicación criptográfica. Obtenga información acerca de cómo cifrar y descifrar contenido en una aplicación Windows Forms.
ms.date: 07/14/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cryptography [NET], example
- cryptography [NET], cryptographic application example
- cryptography [NET], application example
ms.assetid: abf48c11-1e72-431d-9562-39cf23e1a8ff
ms.openlocfilehash: 16a887f23c584daa83106ae61c497bcae8dc4dd2
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87557195"
---
# <a name="walkthrough-creating-a-cryptographic-application"></a><span data-ttu-id="7d22d-104">Tutorial: Crear una aplicación criptográfica</span><span class="sxs-lookup"><span data-stu-id="7d22d-104">Walkthrough: Creating a Cryptographic Application</span></span>

> [!NOTE]
> <span data-ttu-id="7d22d-105">Este artículo se aplica a Windows.</span><span class="sxs-lookup"><span data-stu-id="7d22d-105">This article applies to Windows.</span></span>
>
> <span data-ttu-id="7d22d-106">Para obtener información sobre ASP.NET Core, consulte [ASP.net Core protección de datos](/aspnet/core/security/data-protection/introduction).</span><span class="sxs-lookup"><span data-stu-id="7d22d-106">For information about ASP.NET Core, see [ASP.NET Core Data Protection](/aspnet/core/security/data-protection/introduction).</span></span>

<span data-ttu-id="7d22d-107">En este tutorial se muestra cómo cifrar y descifrar contenido.</span><span class="sxs-lookup"><span data-stu-id="7d22d-107">This walkthrough demonstrates how to encrypt and decrypt content.</span></span> <span data-ttu-id="7d22d-108">Los ejemplos de código están diseñados para una aplicación de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="7d22d-108">The code examples are designed for a Windows Forms application.</span></span> <span data-ttu-id="7d22d-109">Esta aplicación no muestra escenarios del mundo real, como el uso de tarjetas inteligentes.</span><span class="sxs-lookup"><span data-stu-id="7d22d-109">This application does not demonstrate real world scenarios, such as using smart cards.</span></span> <span data-ttu-id="7d22d-110">En su lugar, muestra los aspectos básicos del cifrado y el descifrado.</span><span class="sxs-lookup"><span data-stu-id="7d22d-110">Instead, it demonstrates the fundamentals of encryption and decryption.</span></span>  
  
<span data-ttu-id="7d22d-111">En este tutorial se usan las siguientes directrices para el cifrado:</span><span class="sxs-lookup"><span data-stu-id="7d22d-111">This walkthrough uses the following guidelines for encryption:</span></span>  
  
- <span data-ttu-id="7d22d-112">Use la clase <xref:System.Security.Cryptography.Aes>, un algoritmo simétrico, para cifrar y descifrar datos mediante su <xref:System.Security.Cryptography.SymmetricAlgorithm.Key%2A> y <xref:System.Security.Cryptography.SymmetricAlgorithm.IV%2A> generados automáticamente.</span><span class="sxs-lookup"><span data-stu-id="7d22d-112">Use the <xref:System.Security.Cryptography.Aes> class, a symmetric algorithm, to encrypt and decrypt data by using its automatically generated <xref:System.Security.Cryptography.SymmetricAlgorithm.Key%2A> and <xref:System.Security.Cryptography.SymmetricAlgorithm.IV%2A>.</span></span>  
  
- <span data-ttu-id="7d22d-113">Use el <xref:System.Security.Cryptography.RSA> algoritmo asimétrico para cifrar y descifrar la clave en los datos cifrados por <xref:System.Security.Cryptography.Aes> .</span><span class="sxs-lookup"><span data-stu-id="7d22d-113">Use the <xref:System.Security.Cryptography.RSA> asymmetric algorithm to encrypt and decrypt the key to the data encrypted by <xref:System.Security.Cryptography.Aes>.</span></span> <span data-ttu-id="7d22d-114">Los algoritmos asimétricos son útiles para pequeñas cantidades de datos, como las claves.</span><span class="sxs-lookup"><span data-stu-id="7d22d-114">Asymmetric algorithms are best used for smaller amounts of data, such as a key.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="7d22d-115">Si desea proteger los datos del equipo en lugar de intercambiar contenido cifrado con otras personas, considere la posibilidad de usar la <xref:System.Security.Cryptography.ProtectedData> clase.</span><span class="sxs-lookup"><span data-stu-id="7d22d-115">If you want to protect data on your computer instead of exchanging encrypted content with other people, consider using the <xref:System.Security.Cryptography.ProtectedData> class.</span></span>  
  
 <span data-ttu-id="7d22d-116">En la tabla siguiente se resumen las tareas criptográficas de este tema.</span><span class="sxs-lookup"><span data-stu-id="7d22d-116">The following table summarizes the cryptographic tasks in this topic.</span></span>  
  
|<span data-ttu-id="7d22d-117">Tarea</span><span class="sxs-lookup"><span data-stu-id="7d22d-117">Task</span></span>|<span data-ttu-id="7d22d-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="7d22d-118">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="7d22d-119">Crear una aplicación de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7d22d-119">Creating a Windows Forms application</span></span>|<span data-ttu-id="7d22d-120">Enumera los controles necesarios para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7d22d-120">Lists the controls that are required to run the application.</span></span>|  
|<span data-ttu-id="7d22d-121">Declarar objetos globales</span><span class="sxs-lookup"><span data-stu-id="7d22d-121">Declaring global objects</span></span>|<span data-ttu-id="7d22d-122">Declara variables de ruta de acceso de cadena, los <xref:System.Security.Cryptography.CspParameters> y el <xref:System.Security.Cryptography.RSACryptoServiceProvider> para disponer del contexto global de la clase <xref:System.Windows.Forms.Form>.</span><span class="sxs-lookup"><span data-stu-id="7d22d-122">Declares string path variables, the <xref:System.Security.Cryptography.CspParameters>, and the <xref:System.Security.Cryptography.RSACryptoServiceProvider> to have global context of the <xref:System.Windows.Forms.Form> class.</span></span>|  
|<span data-ttu-id="7d22d-123">Crear una clave asimétrica</span><span class="sxs-lookup"><span data-stu-id="7d22d-123">Creating an asymmetric key</span></span>|<span data-ttu-id="7d22d-124">Crea un par de valores de claves pública y privada asimétricas y le asigna un nombre de contenedor de claves.</span><span class="sxs-lookup"><span data-stu-id="7d22d-124">Creates an asymmetric public and private key value pair and assigns it a key container name.</span></span>|  
|<span data-ttu-id="7d22d-125">Cifrar un archivo</span><span class="sxs-lookup"><span data-stu-id="7d22d-125">Encrypting a file</span></span>|<span data-ttu-id="7d22d-126">Muestra un cuadro de diálogo para seleccionar un archivo para el cifrado y lo cifra.</span><span class="sxs-lookup"><span data-stu-id="7d22d-126">Displays a dialog box to select a file for encryption and encrypts the file.</span></span>|  
|<span data-ttu-id="7d22d-127">Descifrar un archivo</span><span class="sxs-lookup"><span data-stu-id="7d22d-127">Decrypting a file</span></span>|<span data-ttu-id="7d22d-128">Muestra un cuadro de diálogo para seleccionar un archivo cifrado para el descifrado y lo descifra.</span><span class="sxs-lookup"><span data-stu-id="7d22d-128">Displays a dialog box to select an encrypted file for decryption and decrypts the file.</span></span>|  
|<span data-ttu-id="7d22d-129">Obtener una clave privada</span><span class="sxs-lookup"><span data-stu-id="7d22d-129">Getting a private key</span></span>|<span data-ttu-id="7d22d-130">Obtiene el par de claves completo con el nombre del contenedor de claves.</span><span class="sxs-lookup"><span data-stu-id="7d22d-130">Gets the full key pair using the key container name.</span></span>|  
|<span data-ttu-id="7d22d-131">Exportar una clave pública</span><span class="sxs-lookup"><span data-stu-id="7d22d-131">Exporting a public key</span></span>|<span data-ttu-id="7d22d-132">Guarda la clave en un archivo XML únicamente con parámetros públicos.</span><span class="sxs-lookup"><span data-stu-id="7d22d-132">Saves the key to an XML file with only public parameters.</span></span>|  
|<span data-ttu-id="7d22d-133">Importar una clave pública</span><span class="sxs-lookup"><span data-stu-id="7d22d-133">Importing a public key</span></span>|<span data-ttu-id="7d22d-134">Carga la clave desde un archivo XML en el contenedor de claves.</span><span class="sxs-lookup"><span data-stu-id="7d22d-134">Loads the key from an XML file into the key container.</span></span>|  
|<span data-ttu-id="7d22d-135">Probar la aplicación</span><span class="sxs-lookup"><span data-stu-id="7d22d-135">Testing the application</span></span>|<span data-ttu-id="7d22d-136">Enumera los procedimientos para probar esta aplicación.</span><span class="sxs-lookup"><span data-stu-id="7d22d-136">Lists procedures for testing this application.</span></span>|  
  
## <a name="prerequisites"></a><span data-ttu-id="7d22d-137">Prerrequisitos</span><span class="sxs-lookup"><span data-stu-id="7d22d-137">Prerequisites</span></span>  

<span data-ttu-id="7d22d-138">Necesitará los componentes siguientes para completar este tutorial:</span><span class="sxs-lookup"><span data-stu-id="7d22d-138">You need the following components to complete this walkthrough:</span></span>  
  
- <span data-ttu-id="7d22d-139">Referencias a los espacios de nombres <xref:System.IO> y <xref:System.Security.Cryptography>.</span><span class="sxs-lookup"><span data-stu-id="7d22d-139">References to the <xref:System.IO> and <xref:System.Security.Cryptography> namespaces.</span></span>  
  
## <a name="creating-a-windows-forms-application"></a><span data-ttu-id="7d22d-140">Crear una aplicación de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7d22d-140">Creating a Windows Forms Application</span></span>  

<span data-ttu-id="7d22d-141">La mayoría de los ejemplos de código de este tutorial están diseñados para actuar como controladores de eventos de los controles de botón.</span><span class="sxs-lookup"><span data-stu-id="7d22d-141">Most of the code examples in this walkthrough are designed to be event handlers for button controls.</span></span> <span data-ttu-id="7d22d-142">En la tabla siguiente se enumeran los controles necesarios para que la aplicación de ejemplo y los nombres necesarios coincidan con los ejemplos de código.</span><span class="sxs-lookup"><span data-stu-id="7d22d-142">The following table lists the controls required for the sample application and their required names to match the code examples.</span></span>  
  
|<span data-ttu-id="7d22d-143">Control</span><span class="sxs-lookup"><span data-stu-id="7d22d-143">Control</span></span>|<span data-ttu-id="7d22d-144">Nombre</span><span class="sxs-lookup"><span data-stu-id="7d22d-144">Name</span></span>|<span data-ttu-id="7d22d-145">Propiedad de texto (según sea necesario)</span><span class="sxs-lookup"><span data-stu-id="7d22d-145">Text property (as needed)</span></span>|  
|-------------|----------|---------------------------------|  
|<xref:System.Windows.Forms.Button>|`buttonEncryptFile`|<span data-ttu-id="7d22d-146">Cifrar archivo</span><span class="sxs-lookup"><span data-stu-id="7d22d-146">Encrypt File</span></span>|  
|<xref:System.Windows.Forms.Button>|`buttonDecryptFile`|<span data-ttu-id="7d22d-147">Descifrar archivo</span><span class="sxs-lookup"><span data-stu-id="7d22d-147">Decrypt File</span></span>|  
|<xref:System.Windows.Forms.Button>|`buttonCreateAsmKeys`|<span data-ttu-id="7d22d-148">Crear claves</span><span class="sxs-lookup"><span data-stu-id="7d22d-148">Create Keys</span></span>|  
|<xref:System.Windows.Forms.Button>|`buttonExportPublicKey`|<span data-ttu-id="7d22d-149">Exportar la clave pública</span><span class="sxs-lookup"><span data-stu-id="7d22d-149">Export Public Key</span></span>|  
|<xref:System.Windows.Forms.Button>|`buttonImportPublicKey`|<span data-ttu-id="7d22d-150">Importar la clave pública</span><span class="sxs-lookup"><span data-stu-id="7d22d-150">Import Public Key</span></span>|  
|<xref:System.Windows.Forms.Button>|`buttonGetPrivateKey`|<span data-ttu-id="7d22d-151">Obtener la clave privada</span><span class="sxs-lookup"><span data-stu-id="7d22d-151">Get Private Key</span></span>|  
|<xref:System.Windows.Forms.Label>|`label1`|<span data-ttu-id="7d22d-152">Clave no establecida</span><span class="sxs-lookup"><span data-stu-id="7d22d-152">Key not set</span></span>|  
|<xref:System.Windows.Forms.OpenFileDialog>|`openFileDialog1`||  
|<xref:System.Windows.Forms.OpenFileDialog>|`openFileDialog2`||  
  
 <span data-ttu-id="7d22d-153">Haga doble clic en los botones del diseñador de Visual Studio para crear sus controladores de eventos.</span><span class="sxs-lookup"><span data-stu-id="7d22d-153">Double-click the buttons in the Visual Studio designer to create their event handlers.</span></span>
  
## <a name="declaring-global-objects"></a><span data-ttu-id="7d22d-154">Declarar objetos globales</span><span class="sxs-lookup"><span data-stu-id="7d22d-154">Declaring Global Objects</span></span>  

<span data-ttu-id="7d22d-155">Agregue el siguiente código al constructor del formulario.</span><span class="sxs-lookup"><span data-stu-id="7d22d-155">Add the following code to the Form's constructor.</span></span> <span data-ttu-id="7d22d-156">Edite las variables de cadena para el entorno y las preferencias.</span><span class="sxs-lookup"><span data-stu-id="7d22d-156">Edit the string variables for your environment and preferences.</span></span>  
  
[!code-csharp[CryptoWalkThru#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#1)]
[!code-vb[CryptoWalkThru#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#1)]  
  
## <a name="creating-an-asymmetric-key"></a><span data-ttu-id="7d22d-157">Crear una clave asimétrica</span><span class="sxs-lookup"><span data-stu-id="7d22d-157">Creating an Asymmetric Key</span></span>  

<span data-ttu-id="7d22d-158">Esta tarea crea una clave asimétrica que cifra y descifra la clave <xref:System.Security.Cryptography.Aes>.</span><span class="sxs-lookup"><span data-stu-id="7d22d-158">This task creates an asymmetric key that encrypts and decrypts the <xref:System.Security.Cryptography.Aes> key.</span></span> <span data-ttu-id="7d22d-159">Esta clave se usó para cifrar el contenido y muestra el nombre del contenedor de claves en el control de etiqueta.</span><span class="sxs-lookup"><span data-stu-id="7d22d-159">This key was used to encrypt the content and it displays the key container name on the label control.</span></span>  
  
 <span data-ttu-id="7d22d-160">Agregue el siguiente código como controlador de eventos `Click` del botón `Create Keys` (`buttonCreateAsmKeys_Click`).</span><span class="sxs-lookup"><span data-stu-id="7d22d-160">Add the following code as the `Click` event handler for the `Create Keys` button (`buttonCreateAsmKeys_Click`).</span></span>  
  
 [!code-csharp[CryptoWalkThru#2](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#2)]
 [!code-vb[CryptoWalkThru#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#2)]  
  
## <a name="encrypting-a-file"></a><span data-ttu-id="7d22d-161">Cifrar un archivo</span><span class="sxs-lookup"><span data-stu-id="7d22d-161">Encrypting a File</span></span>  

<span data-ttu-id="7d22d-162">Esta tarea implica dos métodos: el método de control de eventos para el `Encrypt File` botón ( `buttonEncryptFile_Click` ) y el `EncryptFile` método.</span><span class="sxs-lookup"><span data-stu-id="7d22d-162">This task involves two methods: the event handler method for the `Encrypt File` button (`buttonEncryptFile_Click`) and the `EncryptFile` method.</span></span> <span data-ttu-id="7d22d-163">El primer método muestra un cuadro de diálogo para seleccionar un archivo y pasa el nombre del archivo al segundo método, que lleva a cabo el cifrado.</span><span class="sxs-lookup"><span data-stu-id="7d22d-163">The first method displays a dialog box for selecting a file and passes the file name to the second method, which performs the encryption.</span></span>  
  
<span data-ttu-id="7d22d-164">El contenido cifrado, la clave y el vector de inicialización (IV) se guardan en un <xref:System.IO.FileStream>, conocido como paquete de cifrado.</span><span class="sxs-lookup"><span data-stu-id="7d22d-164">The encrypted content, key, and IV are all saved to one <xref:System.IO.FileStream>, which is referred to as the encryption package.</span></span>  
  
<span data-ttu-id="7d22d-165">El método `EncryptFile` hace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7d22d-165">The `EncryptFile` method does the following:</span></span>  
  
1. <span data-ttu-id="7d22d-166">Crea un algoritmo simétrico <xref:System.Security.Cryptography.Aes> para cifrar el contenido.</span><span class="sxs-lookup"><span data-stu-id="7d22d-166">Creates a <xref:System.Security.Cryptography.Aes> symmetric algorithm to encrypt the content.</span></span>  
  
2. <span data-ttu-id="7d22d-167">Crea un objeto <xref:System.Security.Cryptography.RSACryptoServiceProvider> para cifrar la clave <xref:System.Security.Cryptography.Aes>.</span><span class="sxs-lookup"><span data-stu-id="7d22d-167">Creates an <xref:System.Security.Cryptography.RSACryptoServiceProvider> object to encrypt the <xref:System.Security.Cryptography.Aes> key.</span></span>  
  
3. <span data-ttu-id="7d22d-168">Usa un objeto <xref:System.Security.Cryptography.CryptoStream> para leer y cifrar el <xref:System.IO.FileStream> del archivo de código fuente, en bloques de bytes, en un objeto <xref:System.IO.FileStream> de destino para el archivo cifrado.</span><span class="sxs-lookup"><span data-stu-id="7d22d-168">Uses a <xref:System.Security.Cryptography.CryptoStream> object to read and encrypt the <xref:System.IO.FileStream> of the source file, in blocks of bytes, into a destination <xref:System.IO.FileStream> object for the encrypted file.</span></span>  
  
4. <span data-ttu-id="7d22d-169">Determina la longitud de la clave cifrada y del IV y crea matrices de bytes de sus valores de longitud.</span><span class="sxs-lookup"><span data-stu-id="7d22d-169">Determines the lengths of the encrypted key and IV, and creates byte arrays of their length values.</span></span>  
  
5. <span data-ttu-id="7d22d-170">Escribe la clave, el IV y sus valores de longitud en el paquete cifrado.</span><span class="sxs-lookup"><span data-stu-id="7d22d-170">Writes the Key, IV, and their length values to the encrypted package.</span></span>  
  
 <span data-ttu-id="7d22d-171">El paquete de cifrado usa el siguiente formato:</span><span class="sxs-lookup"><span data-stu-id="7d22d-171">The encryption package uses the following format:</span></span>  
  
- <span data-ttu-id="7d22d-172">Longitud de clave, bytes 0 - 3</span><span class="sxs-lookup"><span data-stu-id="7d22d-172">Key length, bytes 0 - 3</span></span>  
  
- <span data-ttu-id="7d22d-173">Longitud del IV, bytes 4 - 7</span><span class="sxs-lookup"><span data-stu-id="7d22d-173">IV length, bytes 4 - 7</span></span>  
  
- <span data-ttu-id="7d22d-174">Clave cifrada</span><span class="sxs-lookup"><span data-stu-id="7d22d-174">Encrypted key</span></span>  
  
- <span data-ttu-id="7d22d-175">IV</span><span class="sxs-lookup"><span data-stu-id="7d22d-175">IV</span></span>  
  
- <span data-ttu-id="7d22d-176">Texto cifrado</span><span class="sxs-lookup"><span data-stu-id="7d22d-176">Cipher text</span></span>  
  
 <span data-ttu-id="7d22d-177">Puede usar la longitud de la clave y del IV para determinar los puntos iniciales y la longitud de todas las partes del paquete de cifrado, que posteriormente se puede usar para descifrar el archivo.</span><span class="sxs-lookup"><span data-stu-id="7d22d-177">You can use the lengths of the key and IV to determine the starting points and lengths of all parts of the encryption package, which can then be used to decrypt the file.</span></span>  
  
 <span data-ttu-id="7d22d-178">Agregue el siguiente código como controlador de eventos `Click` del botón `Encrypt File` (`buttonEncryptFile_Click`).</span><span class="sxs-lookup"><span data-stu-id="7d22d-178">Add the following code as the `Click` event handler for the `Encrypt File` button (`buttonEncryptFile_Click`).</span></span>  
  
 [!code-csharp[CryptoWalkThru#3](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#3)]
 [!code-vb[CryptoWalkThru#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#3)]  
  
 <span data-ttu-id="7d22d-179">Agregue el siguiente método `EncryptFile` al formulario.</span><span class="sxs-lookup"><span data-stu-id="7d22d-179">Add the following `EncryptFile` method to the form.</span></span>  
  
 [!code-csharp[CryptoWalkThru#5](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#5)]
 [!code-vb[CryptoWalkThru#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#5)]  
  
## <a name="decrypting-a-file"></a><span data-ttu-id="7d22d-180">Descifrar un archivo</span><span class="sxs-lookup"><span data-stu-id="7d22d-180">Decrypting a File</span></span>  

<span data-ttu-id="7d22d-181">Esta tarea implica dos métodos: el método del controlador de eventos del botón `Decrypt File` (`buttonDecryptFile_Click`) y el método `DecryptFile`.</span><span class="sxs-lookup"><span data-stu-id="7d22d-181">This task involves two methods, the event handler method for the `Decrypt File` button (`buttonDecryptFile_Click`), and the `DecryptFile` method.</span></span> <span data-ttu-id="7d22d-182">El primer método muestra un cuadro de diálogo para seleccionar un archivo y pasa su nombre al segundo método, que lleva a cabo el descifrado.</span><span class="sxs-lookup"><span data-stu-id="7d22d-182">The first method displays a dialog box for selecting a file and passes its file name to the second method, which performs the decryption.</span></span>  
  
<span data-ttu-id="7d22d-183">El método `Decrypt` hace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7d22d-183">The `Decrypt` method does the following:</span></span>  
  
1. <span data-ttu-id="7d22d-184">Crea un <xref:System.Security.Cryptography.Aes> algoritmo simétrico para descifrar el contenido.</span><span class="sxs-lookup"><span data-stu-id="7d22d-184">Creates an <xref:System.Security.Cryptography.Aes> symmetric algorithm to decrypt the content.</span></span>  
  
2. <span data-ttu-id="7d22d-185">Lee los primeros ocho bytes del <xref:System.IO.FileStream> del paquete de cifrado en matrices de bytes para obtener la longitud de la clave cifrada y del IV.</span><span class="sxs-lookup"><span data-stu-id="7d22d-185">Reads the first eight bytes of the <xref:System.IO.FileStream> of the encrypted package into byte arrays to obtain the lengths of the encrypted key and the IV.</span></span>  
  
3. <span data-ttu-id="7d22d-186">Extrae la clave y el IV del paquete de cifrado en matrices de bytes.</span><span class="sxs-lookup"><span data-stu-id="7d22d-186">Extracts the key and IV from the encryption package into byte arrays.</span></span>  
  
4. <span data-ttu-id="7d22d-187">Crea un objeto <xref:System.Security.Cryptography.RSACryptoServiceProvider> para descifrar la clave <xref:System.Security.Cryptography.Aes>.</span><span class="sxs-lookup"><span data-stu-id="7d22d-187">Creates an <xref:System.Security.Cryptography.RSACryptoServiceProvider> object to decrypt the <xref:System.Security.Cryptography.Aes> key.</span></span>  
  
5. <span data-ttu-id="7d22d-188">Usa un objeto <xref:System.Security.Cryptography.CryptoStream> para leer y descifrar la sección de texto cifrado del paquete de cifrado <xref:System.IO.FileStream>, en bloques de bytes, en el objeto <xref:System.IO.FileStream> del archivo descifrado.</span><span class="sxs-lookup"><span data-stu-id="7d22d-188">Uses a <xref:System.Security.Cryptography.CryptoStream> object to read and decrypt the cipher text section of the <xref:System.IO.FileStream> encryption package, in blocks of bytes, into the <xref:System.IO.FileStream> object for the decrypted file.</span></span> <span data-ttu-id="7d22d-189">Al finalizar, se habrá completado el descifrado.</span><span class="sxs-lookup"><span data-stu-id="7d22d-189">When this is finished, the decryption is completed.</span></span>  
  
 <span data-ttu-id="7d22d-190">Agregue el siguiente código como controlador de eventos `Click` del botón `Decrypt File`.</span><span class="sxs-lookup"><span data-stu-id="7d22d-190">Add the following code as the `Click` event handler for the `Decrypt File` button.</span></span>  
  
 [!code-csharp[CryptoWalkThru#4](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#4)]
 [!code-vb[CryptoWalkThru#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#4)]  
  
 <span data-ttu-id="7d22d-191">Agregue el siguiente método `DecryptFile` al formulario.</span><span class="sxs-lookup"><span data-stu-id="7d22d-191">Add the following `DecryptFile` method to the form.</span></span>  
  
 [!code-csharp[CryptoWalkThru#6](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#6)]
 [!code-vb[CryptoWalkThru#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#6)]  
  
## <a name="exporting-a-public-key"></a><span data-ttu-id="7d22d-192">Exportar una clave pública</span><span class="sxs-lookup"><span data-stu-id="7d22d-192">Exporting a Public Key</span></span>

<span data-ttu-id="7d22d-193">Esta tarea guarda en un archivo la clave creada por el botón `Create Keys`.</span><span class="sxs-lookup"><span data-stu-id="7d22d-193">This task saves the key created by the `Create Keys` button to a file.</span></span> <span data-ttu-id="7d22d-194">Solo exporta los parámetros públicos.</span><span class="sxs-lookup"><span data-stu-id="7d22d-194">It exports only the public parameters.</span></span>  
  
<span data-ttu-id="7d22d-195">Esta tarea simula un escenario en que Alicia da a Roberto su clave pública para que pueda cifrar archivos por ella.</span><span class="sxs-lookup"><span data-stu-id="7d22d-195">This task simulates the scenario of Alice giving Bob her public key so that he can encrypt files for her.</span></span> <span data-ttu-id="7d22d-196">Roberto y otras personas que tengan esa clave pública no podrán descifrarlos porque no tienen el par de claves completo con los parámetros privados.</span><span class="sxs-lookup"><span data-stu-id="7d22d-196">He and others who have that public key will not be able to decrypt them because they do not have the full key pair with private parameters.</span></span>  
  
<span data-ttu-id="7d22d-197">Agregue el siguiente código como controlador de eventos `Click` del botón `Export Public Key` (`buttonExportPublicKey_Click`).</span><span class="sxs-lookup"><span data-stu-id="7d22d-197">Add the following code as the `Click` event handler for the `Export Public Key` button (`buttonExportPublicKey_Click`).</span></span>  
  
[!code-csharp[CryptoWalkThru#8](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#8)]
[!code-vb[CryptoWalkThru#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#8)]  
  
## <a name="importing-a-public-key"></a><span data-ttu-id="7d22d-198">Importar una clave pública</span><span class="sxs-lookup"><span data-stu-id="7d22d-198">Importing a Public Key</span></span>

<span data-ttu-id="7d22d-199">Esta tarea carga la clave únicamente con parámetros públicos, tal como se creó con el botón `Export Public Key`, y la establece con el nombre del contenedor de claves.</span><span class="sxs-lookup"><span data-stu-id="7d22d-199">This task loads the key with only public parameters, as created by the `Export Public Key` button, and sets it as the key container name.</span></span>  
  
<span data-ttu-id="7d22d-200">Esta tarea simula un escenario en que Roberto carga la clave de Alicia que solo tiene parámetros públicos, de manera que pueda cifrar archivos por ella.</span><span class="sxs-lookup"><span data-stu-id="7d22d-200">This task simulates the scenario of Bob loading Alice's key with only public parameters so he can encrypt files for her.</span></span>  
  
<span data-ttu-id="7d22d-201">Agregue el siguiente código como controlador de eventos `Click` del botón `Import Public Key` (`buttonImportPublicKey_Click`).</span><span class="sxs-lookup"><span data-stu-id="7d22d-201">Add the following code as the `Click` event handler for the `Import Public Key` button (`buttonImportPublicKey_Click`).</span></span>  
  
[!code-csharp[CryptoWalkThru#9](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#9)]
[!code-vb[CryptoWalkThru#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#9)]  
  
## <a name="getting-a-private-key"></a><span data-ttu-id="7d22d-202">Obtener una clave privada</span><span class="sxs-lookup"><span data-stu-id="7d22d-202">Getting a Private Key</span></span>  

<span data-ttu-id="7d22d-203">Esta tarea establece el nombre del contenedor de claves con el nombre de la clave creada mediante el botón `Create Keys`.</span><span class="sxs-lookup"><span data-stu-id="7d22d-203">This task sets the key container name to the name of the key created by using the `Create Keys` button.</span></span> <span data-ttu-id="7d22d-204">El contenedor de claves contendrá el par de claves completo con los parámetros privados.</span><span class="sxs-lookup"><span data-stu-id="7d22d-204">The key container will contain the full key pair with private parameters.</span></span>  
  
<span data-ttu-id="7d22d-205">Esta tarea simula un escenario en que Alicia usa su clave privada para descifrar archivos cifrados por Roberto.</span><span class="sxs-lookup"><span data-stu-id="7d22d-205">This task simulates the scenario of Alice using her private key to decrypt files encrypted by Bob.</span></span>  
  
<span data-ttu-id="7d22d-206">Agregue el siguiente código como controlador de eventos `Click` del botón `Get Private Key` (`buttonGetPrivateKey_Click`).</span><span class="sxs-lookup"><span data-stu-id="7d22d-206">Add the following code as the `Click` event handler for the `Get Private Key` button (`buttonGetPrivateKey_Click`).</span></span>  
  
[!code-csharp[CryptoWalkThru#7](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#7)]
[!code-vb[CryptoWalkThru#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#7)]  
  
## <a name="testing-the-application"></a><span data-ttu-id="7d22d-207">Probar la aplicación</span><span class="sxs-lookup"><span data-stu-id="7d22d-207">Testing the Application</span></span>

<span data-ttu-id="7d22d-208">Después de haber compilado la aplicación, ejecute los siguientes escenarios de prueba.</span><span class="sxs-lookup"><span data-stu-id="7d22d-208">After you have built the application, perform the following testing scenarios.</span></span>  
  
#### <a name="to-create-keys-encrypt-and-decrypt"></a><span data-ttu-id="7d22d-209">Para crear claves, cifrar y descifrar</span><span class="sxs-lookup"><span data-stu-id="7d22d-209">To create keys, encrypt, and decrypt</span></span>  
  
1. <span data-ttu-id="7d22d-210">Haga clic en el botón `Create Keys`.</span><span class="sxs-lookup"><span data-stu-id="7d22d-210">Click the `Create Keys` button.</span></span> <span data-ttu-id="7d22d-211">La etiqueta muestra el nombre de la clave e indica que se trata de un par de claves completo.</span><span class="sxs-lookup"><span data-stu-id="7d22d-211">The label displays the key name and shows that it is a full key pair.</span></span>  
  
2. <span data-ttu-id="7d22d-212">Haga clic en el botón `Export Public Key`.</span><span class="sxs-lookup"><span data-stu-id="7d22d-212">Click the `Export Public Key` button.</span></span> <span data-ttu-id="7d22d-213">Tenga en cuenta que al exportar los parámetros de la clave pública no se cambia la clave actual.</span><span class="sxs-lookup"><span data-stu-id="7d22d-213">Note that exporting the public key parameters does not change the current key.</span></span>  
  
3. <span data-ttu-id="7d22d-214">Haga clic en el botón `Encrypt File` y seleccione un archivo.</span><span class="sxs-lookup"><span data-stu-id="7d22d-214">Click the `Encrypt File` button and select a file.</span></span>  
  
4. <span data-ttu-id="7d22d-215">Haga clic en el botón `Decrypt File` y seleccione el archivo que acaba de cifrar.</span><span class="sxs-lookup"><span data-stu-id="7d22d-215">Click the `Decrypt File` button and select the file just encrypted.</span></span>  
  
5. <span data-ttu-id="7d22d-216">Examine el archivo que acaba de descifrar.</span><span class="sxs-lookup"><span data-stu-id="7d22d-216">Examine the file just decrypted.</span></span>  
  
6. <span data-ttu-id="7d22d-217">Cierre la aplicación y reiníciela para intentar recuperar los contenedores de claves persistentes en el siguiente escenario.</span><span class="sxs-lookup"><span data-stu-id="7d22d-217">Close the application and restart it to test retrieving persisted key containers in the next scenario.</span></span>  
  
#### <a name="to-encrypt-using-the-public-key"></a><span data-ttu-id="7d22d-218">Para cifrar con la clave pública</span><span class="sxs-lookup"><span data-stu-id="7d22d-218">To encrypt using the public key</span></span>  
  
1. <span data-ttu-id="7d22d-219">Haga clic en el botón `Import Public Key`.</span><span class="sxs-lookup"><span data-stu-id="7d22d-219">Click the `Import Public Key` button.</span></span> <span data-ttu-id="7d22d-220">La etiqueta muestra el nombre de la clave e indica que solo es pública.</span><span class="sxs-lookup"><span data-stu-id="7d22d-220">The label displays the key name and shows that it is public only.</span></span>  
  
2. <span data-ttu-id="7d22d-221">Haga clic en el botón `Encrypt File` y seleccione un archivo.</span><span class="sxs-lookup"><span data-stu-id="7d22d-221">Click the `Encrypt File` button and select a file.</span></span>  
  
3. <span data-ttu-id="7d22d-222">Haga clic en el botón `Decrypt File` y seleccione el archivo que acaba de cifrar.</span><span class="sxs-lookup"><span data-stu-id="7d22d-222">Click the `Decrypt File` button and select the file just encrypted.</span></span> <span data-ttu-id="7d22d-223">Esto generará un error porque debe disponer de la clave privada para efectuar el descifrado.</span><span class="sxs-lookup"><span data-stu-id="7d22d-223">This will fail because you must have the private key to decrypt.</span></span>  
  
 <span data-ttu-id="7d22d-224">En este escenario se muestra una situación en la que solo se dispone de la clave pública para cifrar un archivo para otra persona.</span><span class="sxs-lookup"><span data-stu-id="7d22d-224">This scenario demonstrates having only the public key to encrypt a file for another person.</span></span> <span data-ttu-id="7d22d-225">Normalmente, esa persona debe proporcionarle únicamente la clave pública y conservar la clave privada para el descifrado.</span><span class="sxs-lookup"><span data-stu-id="7d22d-225">Typically that person would give you only the public key and withhold the private key for decryption.</span></span>  
  
#### <a name="to-decrypt-using-the-private-key"></a><span data-ttu-id="7d22d-226">Para descifrar con la clave privada</span><span class="sxs-lookup"><span data-stu-id="7d22d-226">To decrypt using the private key</span></span>  
  
1. <span data-ttu-id="7d22d-227">Haga clic en el botón `Get Private Key`.</span><span class="sxs-lookup"><span data-stu-id="7d22d-227">Click the `Get Private Key` button.</span></span> <span data-ttu-id="7d22d-228">La etiqueta muestra el nombre de la clave e indica si se trata del par de claves completo.</span><span class="sxs-lookup"><span data-stu-id="7d22d-228">The label displays the key name and shows whether it is the full key pair.</span></span>  
  
2. <span data-ttu-id="7d22d-229">Haga clic en el botón `Decrypt File` y seleccione el archivo que acaba de cifrar.</span><span class="sxs-lookup"><span data-stu-id="7d22d-229">Click the `Decrypt File` button and select the file just encrypted.</span></span> <span data-ttu-id="7d22d-230">Esta acción se llevará a cabo correctamente porque dispone del par de claves completo para efectuar el descifrado.</span><span class="sxs-lookup"><span data-stu-id="7d22d-230">This will be successful because you have the full key pair to decrypt.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d22d-231">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7d22d-231">See also</span></span>

- <span data-ttu-id="7d22d-232">[Modelo de criptografía](cryptography-model.md) : describe cómo se implementa la criptografía en la biblioteca de clases base.</span><span class="sxs-lookup"><span data-stu-id="7d22d-232">[Cryptography Model](cryptography-model.md) - Describes how cryptography is implemented in the base class library.</span></span>
- [<span data-ttu-id="7d22d-233">servicios criptográficos</span><span class="sxs-lookup"><span data-stu-id="7d22d-233">Cryptographic Services</span></span>](cryptographic-services.md)
- [<span data-ttu-id="7d22d-234">Criptografía multiplataforma</span><span class="sxs-lookup"><span data-stu-id="7d22d-234">Cross-Platform Cryptography</span></span>](cross-platform-cryptography.md)
- [<span data-ttu-id="7d22d-235">ASP.NET Core protección de datos</span><span class="sxs-lookup"><span data-stu-id="7d22d-235">ASP.NET Core Data Protection</span></span>](/aspnet/core/security/data-protection/introduction)
