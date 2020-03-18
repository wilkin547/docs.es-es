---
title: 'Cómo: Descargar un archivo'
ms.date: 07/20/2015
helpviewer_keywords:
- downloading Internet resources [Visual Basic], files
- downloading files [Visual Basic]
- remote computers [Visual Basic], downloading from
- files [Visual Basic], downloading
- files [Visual Basic], transferring
ms.assetid: ac479f81-c0e2-4b99-af73-217f446b73da
ms.openlocfilehash: 4923feb46ff638de9514a4d70fc00367491a6f44
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "74345619"
---
# <a name="how-to-download-a-file-in-visual-basic"></a><span data-ttu-id="c1290-102">Cómo: Descargar un archivo en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c1290-102">How to: Download a File in Visual Basic</span></span>

<span data-ttu-id="c1290-103">El método <xref:Microsoft.VisualBasic.Devices.Network.DownloadFile%2A> se puede usar para descargar un archivo remoto y almacenarlo en una ubicación específica.</span><span class="sxs-lookup"><span data-stu-id="c1290-103">The <xref:Microsoft.VisualBasic.Devices.Network.DownloadFile%2A> method can be used to download a remote file and store it to a specific location.</span></span> <span data-ttu-id="c1290-104">Si el parámetro `ShowUI` se establece en `True`, se abre un cuadro de diálogo que muestra el progreso de la descarga y permite a los usuarios cancelar la operación.</span><span class="sxs-lookup"><span data-stu-id="c1290-104">If the `ShowUI` parameter is set to `True`, a dialog box is displayed showing the progress of the download and allowing users to cancel the operation.</span></span> <span data-ttu-id="c1290-105">De forma predeterminada, no se sobrescriben los archivos existentes que tengan el mismo nombre. Si quiere sobrescribir los archivos existentes, establezca el parámetro `overwrite` en `True`.</span><span class="sxs-lookup"><span data-stu-id="c1290-105">By default, existing files having the same name are not overwritten; if you want to overwrite existing files, set the `overwrite` parameter to `True`.</span></span>

<span data-ttu-id="c1290-106">Las condiciones siguientes pueden provocar una excepción:</span><span class="sxs-lookup"><span data-stu-id="c1290-106">The following conditions may cause an exception:</span></span>

- <span data-ttu-id="c1290-107">El nombre de unidad no es válido (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="c1290-107">Drive name is not valid (<xref:System.ArgumentException>).</span></span>

- <span data-ttu-id="c1290-108">No se ha proporcionado la autenticación necesaria (<xref:System.UnauthorizedAccessException> o <xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="c1290-108">Necessary authentication has not been supplied (<xref:System.UnauthorizedAccessException> or <xref:System.Security.SecurityException>).</span></span>

- <span data-ttu-id="c1290-109">El servidor no responde en el `connectionTimeout` especificado (<xref:System.TimeoutException>).</span><span class="sxs-lookup"><span data-stu-id="c1290-109">The server does not respond within the specified `connectionTimeout` (<xref:System.TimeoutException>).</span></span>

- <span data-ttu-id="c1290-110">El sitio web ha denegado la solicitud (<xref:System.Net.WebException>).</span><span class="sxs-lookup"><span data-stu-id="c1290-110">The request is denied by the Web site (<xref:System.Net.WebException>).</span></span>

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

> [!IMPORTANT]
> <span data-ttu-id="c1290-111">No tome ninguna decisión sobre el contenido del archivo basándose en su nombre.</span><span class="sxs-lookup"><span data-stu-id="c1290-111">Do not make decisions about the contents of the file based on the name of the file.</span></span> <span data-ttu-id="c1290-112">Por ejemplo, es posible que el archivo Form1.vb no sea un archivo de código fuente de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="c1290-112">For example, the file Form1.vb may not be a Visual Basic source file.</span></span> <span data-ttu-id="c1290-113">Compruebe todas las entradas antes de utilizar los datos en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c1290-113">Verify all inputs before using the data in your application.</span></span> <span data-ttu-id="c1290-114">Puede que el contenido del archivo no sea el esperado y que los métodos que leen el archivo produzcan un error.</span><span class="sxs-lookup"><span data-stu-id="c1290-114">The contents of the file may not be what is expected, and methods to read from the file may fail.</span></span>

### <a name="to-download-a-file"></a><span data-ttu-id="c1290-115">Para descargar un archivo</span><span class="sxs-lookup"><span data-stu-id="c1290-115">To download a file</span></span>

- <span data-ttu-id="c1290-116">Use el método `DownloadFile` para descargar el archivo, especificando la ubicación del archivo de destino como una cadena o un identificador URI, y la ubicación en la que se va a almacenar el archivo.</span><span class="sxs-lookup"><span data-stu-id="c1290-116">Use the `DownloadFile` method to download the file, specifying the target file's location as a string or URI and specifying the location at which to store the file.</span></span> <span data-ttu-id="c1290-117">En este ejemplo se descarga el archivo `WineList.txt` de `http://www.cohowinery.com/downloads` y se guarda en `C:\Documents and Settings\All Users\Documents`:</span><span class="sxs-lookup"><span data-stu-id="c1290-117">This example downloads the file `WineList.txt` from `http://www.cohowinery.com/downloads` and saves it to `C:\Documents and Settings\All Users\Documents`:</span></span>

  [!code-vb[VbResourceTasks#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#9)]

### <a name="to-download-a-file-specifying-a-time-out-interval"></a><span data-ttu-id="c1290-118">Para descargar un archivo, especificando un intervalo de tiempo de espera</span><span class="sxs-lookup"><span data-stu-id="c1290-118">To download a file, specifying a time-out interval</span></span>

- <span data-ttu-id="c1290-119">Use el método `DownloadFile` para descargar el archivo, especificando la ubicación del archivo de destino como una cadena o un identificador URI, la ubicación en la que se va a almacenar el archivo y el intervalo de tiempo de espera en milisegundos (el valor predeterminado es 1000).</span><span class="sxs-lookup"><span data-stu-id="c1290-119">Use the `DownloadFile` method to download the file, specifying the target file's location as a string or URI, specifying the location at which to store the file, and specifying the time-out interval in milliseconds (the default is 1000).</span></span> <span data-ttu-id="c1290-120">En este ejemplo se descarga el archivo `WineList.txt` de `http://www.cohowinery.com/downloads` y se guarda en `C:\Documents and Settings\All Users\Documents`, especificando un intervalo de tiempo de espera de 500 milisegundos:</span><span class="sxs-lookup"><span data-stu-id="c1290-120">This example downloads the file `WineList.txt` from `http://www.cohowinery.com/downloads` and saves it to `C:\Documents and Settings\All Users\Documents`, specifying a time-out interval of 500 milliseconds:</span></span>

  [!code-vb[VbResourceTasks#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#10)]

### <a name="to-download-a-file-supplying-a-user-name-and-password"></a><span data-ttu-id="c1290-121">Para descargar un archivo, proporcionando un nombre de usuario y contraseña</span><span class="sxs-lookup"><span data-stu-id="c1290-121">To download a file, supplying a user name and password</span></span>

- <span data-ttu-id="c1290-122">Use el método `DownLoadFile` para descargar el archivo, especificando la ubicación del archivo de destino como una cadena o un identificador URI, y la ubicación en la que se va a almacenar el archivo, el nombre de usuario y la contraseña.</span><span class="sxs-lookup"><span data-stu-id="c1290-122">Use the `DownLoadFile` method to download the file, specifying the target file's location as a string or URI and specifying the location at which to store the file, the user name, and the password.</span></span> <span data-ttu-id="c1290-123">En este ejemplo se descarga el archivo `WineList.txt` de `http://www.cohowinery.com/downloads` y se guarda en `C:\Documents and Settings\All Users\Documents`, con el nombre de usuario `anonymous` y una contraseña en blanco.</span><span class="sxs-lookup"><span data-stu-id="c1290-123">This example downloads the file `WineList.txt` from `http://www.cohowinery.com/downloads` and saves it to `C:\Documents and Settings\All Users\Documents`, with the user name `anonymous` and a blank password.</span></span>

  [!code-vb[VbResourceTasks#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#11)]

  > [!IMPORTANT]
  > <span data-ttu-id="c1290-124">El protocolo FTP que usa el método `DownLoadFile` envía información, incluidas las contraseñas, en texto sin formato y no debe usarse para transmitir información confidencial.</span><span class="sxs-lookup"><span data-stu-id="c1290-124">The FTP protocol used by the `DownLoadFile` method sends information, including passwords, in plain text and should not be used for transmitting sensitive information.</span></span>

## <a name="see-also"></a><span data-ttu-id="c1290-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="c1290-125">See also</span></span>

- <xref:Microsoft.VisualBasic.Devices.Network>
- <xref:Microsoft.VisualBasic.Devices.Network.DownloadFile%2A>
- [<span data-ttu-id="c1290-126">Cargar un archivo</span><span class="sxs-lookup"><span data-stu-id="c1290-126">How to: Upload a File</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-upload-a-file.md)
- [<span data-ttu-id="c1290-127">Analizar rutas de acceso a archivos</span><span class="sxs-lookup"><span data-stu-id="c1290-127">How to: Parse File Paths</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)
