---
title: 'Cómo: Escribir texto en archivos'
ms.date: 07/20/2015
helpviewer_keywords:
- files [Visual Basic], writing to
- text, writing to files
- writing to files [Visual Basic]
- examples [Visual Basic], text files
ms.assetid: 304956eb-530d-4df7-b48f-9b4d1f2581a0
ms.openlocfilehash: f95a0c4df4a2eab0069a6dab0d4c3fa338d1d8ef
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84411543"
---
# <a name="how-to-write-text-to-files-in-visual-basic"></a><span data-ttu-id="26cbb-102">Cómo: Escribir texto en archivos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="26cbb-102">How to: Write Text to Files in Visual Basic</span></span>

<span data-ttu-id="26cbb-103">El método <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A> se puede usar para escribir texto en archivos.</span><span class="sxs-lookup"><span data-stu-id="26cbb-103">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A> method can be used to write text to files.</span></span> <span data-ttu-id="26cbb-104">Si el archivo especificado no existe, se crea.</span><span class="sxs-lookup"><span data-stu-id="26cbb-104">If the specified file does not exist, it is created.</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="26cbb-105">Procedimiento</span><span class="sxs-lookup"><span data-stu-id="26cbb-105">Procedure</span></span>  
  
#### <a name="to-write-text-to-a-file"></a><span data-ttu-id="26cbb-106">Para escribir texto en un archivo</span><span class="sxs-lookup"><span data-stu-id="26cbb-106">To write text to a file</span></span>  
  
- <span data-ttu-id="26cbb-107">Use el método `WriteAllText` para escribir el texto en un archivo, especificando el archivo y el texto que se va a escribir.</span><span class="sxs-lookup"><span data-stu-id="26cbb-107">Use the `WriteAllText` method to write text to a file, specifying the file and text to be written.</span></span> <span data-ttu-id="26cbb-108">Este ejemplo escribe la línea `"This is new text."` en el archivo denominado `test.txt`, anexando el texto al texto existente en el archivo.</span><span class="sxs-lookup"><span data-stu-id="26cbb-108">This example writes the line `"This is new text."` to the file named `test.txt`, appending the text to any existing text in the file.</span></span>  
  
     [!code-vb[VbFileIOWrite#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOWrite/VB/Class1.vb#3)]  
  
#### <a name="to-write-a-series-of-strings-to-a-file"></a><span data-ttu-id="26cbb-109">Para escribir una serie de cadenas en un archivo</span><span class="sxs-lookup"><span data-stu-id="26cbb-109">To write a series of strings to a file</span></span>  
  
- <span data-ttu-id="26cbb-110">Recorra en iteración la colección de cadenas.</span><span class="sxs-lookup"><span data-stu-id="26cbb-110">Loop through the string collection.</span></span> <span data-ttu-id="26cbb-111">Use el método `WriteAllText` para escribir el texto en un archivo, especificando el archivo de destino, la cadena que se debe agregar y estableciendo `append` en `True`.</span><span class="sxs-lookup"><span data-stu-id="26cbb-111">Use the `WriteAllText` method to write text to a file, specifying the target file and string to be added and setting `append` to `True`.</span></span>  
  
     <span data-ttu-id="26cbb-112">En este ejemplo se escriben los nombres de los archivos contenidos en el directorio `Documents and Settings` en `FileList.txt`, insertando un retorno de carro entre cada uno de ellos para una mejor legibilidad.</span><span class="sxs-lookup"><span data-stu-id="26cbb-112">This example writes the names of the files in the `Documents and Settings` directory to `FileList.txt`, inserting a carriage return between each for better readability.</span></span>  
  
     [!code-vb[VbFileIOWrite#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOWrite/VB/Class1.vb#4)]  
  
## <a name="robust-programming"></a><span data-ttu-id="26cbb-113">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="26cbb-113">Robust Programming</span></span>  

 <span data-ttu-id="26cbb-114">Las condiciones siguientes pueden provocar una excepción:</span><span class="sxs-lookup"><span data-stu-id="26cbb-114">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="26cbb-115">La ruta de acceso no es válida por una de las siguientes razones: es una cadena de longitud cero, solo contiene un espacio en blanco, contiene caracteres no válidos o es una ruta de acceso de dispositivo (empieza por \\\\.\\) (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="26cbb-115">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (starts with \\\\.\\) (<xref:System.ArgumentException>).</span></span>  
  
- <span data-ttu-id="26cbb-116">La ruta de acceso no es válida porque es `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="26cbb-116">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
- <span data-ttu-id="26cbb-117">`File` apunta a una ruta de acceso que no existe (<xref:System.IO.FileNotFoundException> o <xref:System.IO.DirectoryNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="26cbb-117">`File` points to a path that does not exist (<xref:System.IO.FileNotFoundException> or <xref:System.IO.DirectoryNotFoundException>).</span></span>  
  
- <span data-ttu-id="26cbb-118">El archivo está en uso por otro proceso o hay un error de E/S (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="26cbb-118">The file is in use by another process, or an I/O error occurs (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="26cbb-119">La ruta supera la longitud máxima definida por el sistema (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="26cbb-119">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>  
  
- <span data-ttu-id="26cbb-120">Un nombre de archivo o de directorio de la ruta de acceso contiene un signo de dos puntos (:) o tiene un formato no válido (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="26cbb-120">A file or directory name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>  
  
- <span data-ttu-id="26cbb-121">El usuario no tiene los permisos necesarios para ver la ruta de acceso (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="26cbb-121">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>  
  
- <span data-ttu-id="26cbb-122">El disco está lleno y se produce un error en la llamada a `WriteAllText` (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="26cbb-122">The disk is full, and the call to `WriteAllText` fails (<xref:System.IO.IOException>).</span></span>  
  
 <span data-ttu-id="26cbb-123">Si realiza una ejecución en un contexto de confianza parcial, el código podría desencadenar una excepción por falta de privilegios.</span><span class="sxs-lookup"><span data-stu-id="26cbb-123">If you are running in a partial-trust context, the code might throw an exception due to insufficient privileges.</span></span> <span data-ttu-id="26cbb-124">Para obtener más información, vea [Code Access Security Basics](../../../../framework/misc/code-access-security-basics.md) (Aspectos básicos de seguridad de acceso del código).</span><span class="sxs-lookup"><span data-stu-id="26cbb-124">For more information, see [Code Access Security Basics](../../../../framework/misc/code-access-security-basics.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26cbb-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="26cbb-125">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A>
- [<span data-ttu-id="26cbb-126">Leer de archivos de texto</span><span class="sxs-lookup"><span data-stu-id="26cbb-126">How to: Read from Text Files</span></span>](how-to-read-from-text-files.md)
