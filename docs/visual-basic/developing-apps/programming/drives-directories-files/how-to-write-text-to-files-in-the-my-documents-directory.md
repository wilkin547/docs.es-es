---
title: 'Cómo: Escribir texto en archivos del directorio Mis documentos'
ms.date: 07/20/2015
helpviewer_keywords:
- files [Visual Basic], writing to
- text, writing to files
- examples [Visual Basic], text files
- writing to files [Visual Basic], in My Documents
ms.assetid: 1c726124-781d-4976-9baa-ed46814ff3fe
ms.openlocfilehash: bb3a9bdc44f86fbcdb3c56ee088740efdfebe95d
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90546463"
---
# <a name="how-to-write-text-to-files-in-the-my-documents-directory-in-visual-basic"></a><span data-ttu-id="d65cd-102">Cómo: Escribir texto en archivos del directorio Mis documentos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d65cd-102">How to: Write Text to Files in the My Documents Directory in Visual Basic</span></span>

<span data-ttu-id="d65cd-103">El objeto `My.Computer.FileSystem.SpecialDirectories` le permite tener acceso a los directorios especiales, como el directorio **MyDocuments**.</span><span class="sxs-lookup"><span data-stu-id="d65cd-103">The `My.Computer.FileSystem.SpecialDirectories` object allows you to access special directories, such as the **MyDocuments** directory.</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="d65cd-104">Procedimiento</span><span class="sxs-lookup"><span data-stu-id="d65cd-104">Procedure</span></span>  
  
#### <a name="to-write-new-text-files-in-the-my-documents-directory"></a><span data-ttu-id="d65cd-105">Para escribir nuevos archivos de texto en el directorio Mis documentos</span><span class="sxs-lookup"><span data-stu-id="d65cd-105">To write new text files in the My Documents directory</span></span>  
  
1. <span data-ttu-id="d65cd-106">Use la propiedad `My.Computer.FileSystem.SpecialDirectories.MyDocuments` para proporcionar la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="d65cd-106">Use the `My.Computer.FileSystem.SpecialDirectories.MyDocuments` property to supply the path.</span></span>  
  
     [!code-vb[VbFileIOWrite#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOWrite/VB/Class1.vb#1)]  
  
2. <span data-ttu-id="d65cd-107">Use el método `WriteAllText` para escribir texto en el archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="d65cd-107">Use the `WriteAllText` method to write text to the specified file.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#14)]  
  
## <a name="example"></a><span data-ttu-id="d65cd-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d65cd-108">Example</span></span>  

 [!code-vb[VbFileIOWrite#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOWrite/VB/Class1.vb#2)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d65cd-109">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="d65cd-109">Compiling the Code</span></span>  

 <span data-ttu-id="d65cd-110">Reemplace `test.txt` por el nombre del archivo en el que quiere escribir.</span><span class="sxs-lookup"><span data-stu-id="d65cd-110">Replace `test.txt` with the name of the file you want to write to.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="d65cd-111">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="d65cd-111">Robust Programming</span></span>  

 <span data-ttu-id="d65cd-112">Este código vuelve a producir todas las excepciones que pueden ocurrir al escribir texto en el archivo.</span><span class="sxs-lookup"><span data-stu-id="d65cd-112">This code rethrows all the exceptions that may occur when writing text to the file.</span></span> <span data-ttu-id="d65cd-113">Puede reducir la probabilidad de que se produzcan excepciones usando los controles de Windows Forms como los componentes [OpenFileDialog](/dotnet/desktop/winforms/controls/openfiledialog-component-windows-forms) y [SaveFileDialog](/dotnet/desktop/winforms/controls/savefiledialog-component-windows-forms), que limitan las opciones del usuario a los nombres de archivo válidos.</span><span class="sxs-lookup"><span data-stu-id="d65cd-113">You can reduce the likelihood of exceptions by using Windows Forms controls such as the [OpenFileDialog](/dotnet/desktop/winforms/controls/openfiledialog-component-windows-forms) and the [SaveFileDialog](/dotnet/desktop/winforms/controls/savefiledialog-component-windows-forms) components that limit the user choices to valid file names.</span></span> <span data-ttu-id="d65cd-114">En cambio, el uso de estos controles no es infalible.</span><span class="sxs-lookup"><span data-stu-id="d65cd-114">Using these controls is not foolproof, however.</span></span> <span data-ttu-id="d65cd-115">El sistema de archivos puede cambiar entre el momento en el que el usuario selecciona un archivo y el momento en el que se ejecuta el código.</span><span class="sxs-lookup"><span data-stu-id="d65cd-115">The file system can change between the time the user selects a file and the time that the code executes.</span></span> <span data-ttu-id="d65cd-116">Por ello, cuando se trabaja con archivos casi siempre es prácticamente necesario realizar un control de excepciones.</span><span class="sxs-lookup"><span data-stu-id="d65cd-116">Exception handling is therefore nearly always necessary when with working with files.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="d65cd-117">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="d65cd-117">.NET Framework Security</span></span>  

 <span data-ttu-id="d65cd-118">Si realiza una ejecución en un contexto de confianza parcial, el código podría desencadenar una excepción por falta de privilegios.</span><span class="sxs-lookup"><span data-stu-id="d65cd-118">If you are running in a partial-trust context, the code might throw an exception due to insufficient privileges.</span></span> <span data-ttu-id="d65cd-119">Para obtener más información, vea [Code Access Security Basics](../../../../framework/misc/code-access-security-basics.md) (Aspectos básicos de seguridad de acceso del código).</span><span class="sxs-lookup"><span data-stu-id="d65cd-119">For more information, see [Code Access Security Basics](../../../../framework/misc/code-access-security-basics.md).</span></span>  
  
 <span data-ttu-id="d65cd-120">En este ejemplo se crea un nuevo archivo.</span><span class="sxs-lookup"><span data-stu-id="d65cd-120">This example creates a new file.</span></span> <span data-ttu-id="d65cd-121">Si una aplicación necesita crear un archivo, precisará permisos de creación para la carpeta correspondiente.</span><span class="sxs-lookup"><span data-stu-id="d65cd-121">If an application needs to create a file, that application needs Create permission for the folder.</span></span> <span data-ttu-id="d65cd-122">Los permisos se establecen usando listas de control de acceso.</span><span class="sxs-lookup"><span data-stu-id="d65cd-122">Permissions are set using access control lists.</span></span> <span data-ttu-id="d65cd-123">Si el archivo ya existe, la aplicación solo necesitará permiso de escritura, un privilegio menor.</span><span class="sxs-lookup"><span data-stu-id="d65cd-123">If the file already exists, the application needs only Write permission, a lesser privilege.</span></span> <span data-ttu-id="d65cd-124">Siempre que sea posible, resulta más seguro crear el archivo durante la implementación y conceder solo privilegios de lectura en un solo archivo, en lugar de privilegios de creación para una carpeta.</span><span class="sxs-lookup"><span data-stu-id="d65cd-124">Where possible, it is more secure to create the file during deployment, and only grant Read privileges to a single file, rather than to grant Create privileges for a folder.</span></span> <span data-ttu-id="d65cd-125">También es más seguro escribir datos en carpetas de usuario en lugar de en la carpeta raíz o en la carpeta **Archivos de programa**.</span><span class="sxs-lookup"><span data-stu-id="d65cd-125">Also, it is more secure to write data to user folders than to the root folder or the **Program Files** folder.</span></span> <span data-ttu-id="d65cd-126">Para obtener más información, vea [Información general sobre la tecnología ACL](/previous-versions/dotnet/netframework-4.0/ms229742(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="d65cd-126">For more information, see [ACL Technology Overview](/previous-versions/dotnet/netframework-4.0/ms229742(v=vs.100)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d65cd-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="d65cd-127">See also</span></span>

- <xref:System.IO.Path.Combine%2A?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Devices.Computer>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A>
- <xref:Microsoft.VisualBasic.FileIO.SpecialDirectories>
