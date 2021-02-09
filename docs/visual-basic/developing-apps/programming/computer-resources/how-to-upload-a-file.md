---
description: 'Más información acerca de: Procedimiento: para cargar un archivo en Visual Basic'
title: Procedimiento para cargar un archivo
ms.date: 07/20/2015
helpviewer_keywords:
- networks, uploading files
- files [Visual Basic], uploading
- uploading files [Visual Basic]
- UploadFile method [Visual Basic]
- My.Computer.Network.UploadFile method
ms.assetid: a8b37924-c523-4fd3-b5ca-cb0074df29cd
ms.openlocfilehash: d38820cda6a143cf3f06bf6a2ca72cba5a9f3aef
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99675408"
---
# <a name="how-to-upload-a-file-in-visual-basic"></a><span data-ttu-id="6c67e-103">Cómo: Cargar un archivo en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6c67e-103">How to: Upload a File in Visual Basic</span></span>

<span data-ttu-id="6c67e-104">El método <xref:Microsoft.VisualBasic.Devices.Network.UploadFile%2A> se puede usar para cargar un archivo y almacenarlo en una ubicación remota.</span><span class="sxs-lookup"><span data-stu-id="6c67e-104">The <xref:Microsoft.VisualBasic.Devices.Network.UploadFile%2A> method can be used to upload a file and store it to a remote location.</span></span> <span data-ttu-id="6c67e-105">Si el parámetro `ShowUI` se establece en `True`, aparece un cuadro de diálogo que muestra el progreso de la carga y permite a los usuarios cancelar la operación.</span><span class="sxs-lookup"><span data-stu-id="6c67e-105">If the `ShowUI` parameter is set to `True`, a dialog box is displayed that shows the progress of the upload and allows users to cancel the operation.</span></span>  
  
### <a name="to-upload-a-file"></a><span data-ttu-id="6c67e-106">Para cargar un archivo</span><span class="sxs-lookup"><span data-stu-id="6c67e-106">To upload a file</span></span>  
  
- <span data-ttu-id="6c67e-107">Use el método `UploadFile` para cargar un archivo; especifique la ubicación del archivo de código fuente y la ubicación del directorio de destino como una cadena o un identificador uniforme de recursos (URI). En este ejemplo se carga el archivo `Order.txt` en `http://www.cohowinery.com/uploads.aspx`.</span><span class="sxs-lookup"><span data-stu-id="6c67e-107">Use the `UploadFile` method to upload a file, specifying the source file's location and the target directory location as a string or URI (Uniform Resource Identifier).This example uploads the file `Order.txt` to `http://www.cohowinery.com/uploads.aspx`.</span></span>  
  
     [!code-vb[VbResourceTasks#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#6)]  
  
### <a name="to-upload-a-file-and-show-the-progress-of-the-operation"></a><span data-ttu-id="6c67e-108">Para cargar un archivo y mostrar el progreso de la operación</span><span class="sxs-lookup"><span data-stu-id="6c67e-108">To upload a file and show the progress of the operation</span></span>  
  
- <span data-ttu-id="6c67e-109">Use el método `UploadFile` para cargar un archivo; especifique la ubicación del archivo de código fuente y la ubicación del directorio de destino como una cadena o un URI.</span><span class="sxs-lookup"><span data-stu-id="6c67e-109">Use the `UploadFile` method to upload a file, specifying the source file's location and the target directory location as a string or URI.</span></span> <span data-ttu-id="6c67e-110">En este ejemplo se carga el archivo `Order.txt` en `http://www.cohowinery.com/uploads.aspx` sin indicar un nombre de usuario ni contraseña, se muestra el progreso de la carga y se cuenta con un intervalo de tiempo de espera de 500 milisegundos.</span><span class="sxs-lookup"><span data-stu-id="6c67e-110">This example uploads the file `Order.txt` to `http://www.cohowinery.com/uploads.aspx` without supplying a user name or password, shows the progress of the upload, and has a time-out interval of 500 milliseconds.</span></span>  
  
     [!code-vb[VbResourceTasks#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#7)]  
  
### <a name="to-upload-a-file-supplying-a-user-name-and-password"></a><span data-ttu-id="6c67e-111">Para cargar un archivo, proporcionando un nombre de usuario y contraseña</span><span class="sxs-lookup"><span data-stu-id="6c67e-111">To upload a file, supplying a user name and password</span></span>  
  
- <span data-ttu-id="6c67e-112">Use el método `UploadFile` para cargar un archivo; especifique la ubicación del archivo de código fuente y la ubicación del directorio de destino como una cadena o un URI e indique el nombre de usuario y la contraseña.</span><span class="sxs-lookup"><span data-stu-id="6c67e-112">Use the `UploadFile` method to upload a file, specifying the source file's location and the target directory location as a string or URI, and specifying the user name and the password.</span></span> <span data-ttu-id="6c67e-113">En este ejemplo se carga el archivo `Order.txt` en `http://www.cohowinery.com/uploads.aspx`, proporcionando el nombre de usuario `anonymous` y una contraseña en blanco.</span><span class="sxs-lookup"><span data-stu-id="6c67e-113">This example uploads the file `Order.txt` to `http://www.cohowinery.com/uploads.aspx`, supplying the user name `anonymous` and a blank password.</span></span>  
  
     [!code-vb[VbResourceTasks#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#8)]  
  
## <a name="robust-programming"></a><span data-ttu-id="6c67e-114">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="6c67e-114">Robust Programming</span></span>  

 <span data-ttu-id="6c67e-115">Las siguientes condiciones pueden provocar una excepción:</span><span class="sxs-lookup"><span data-stu-id="6c67e-115">The following conditions may throw an exception:</span></span>  
  
- <span data-ttu-id="6c67e-116">La ruta de acceso de archivo local no es válida (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="6c67e-116">The local file path is not valid (<xref:System.ArgumentException>).</span></span>  
  
- <span data-ttu-id="6c67e-117">Error de autenticación (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="6c67e-117">Authentication failed (<xref:System.Security.SecurityException>).</span></span>  
  
- <span data-ttu-id="6c67e-118">Se agotó el tiempo de espera de la conexión (<xref:System.TimeoutException>).</span><span class="sxs-lookup"><span data-stu-id="6c67e-118">The connection timed out (<xref:System.TimeoutException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c67e-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="6c67e-119">See also</span></span>

- <xref:Microsoft.VisualBasic.Devices.Network?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Devices.Network.UploadFile%2A>
- [<span data-ttu-id="6c67e-120">Procedimiento para descargar un archivo</span><span class="sxs-lookup"><span data-stu-id="6c67e-120">How to: Download a File</span></span>](how-to-download-a-file.md)
- [<span data-ttu-id="6c67e-121">Procedimiento para analizar rutas de acceso a archivos</span><span class="sxs-lookup"><span data-stu-id="6c67e-121">How to: Parse File Paths</span></span>](../drives-directories-files/how-to-parse-file-paths.md)
