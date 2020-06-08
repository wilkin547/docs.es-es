---
title: 'Cómo: Escribir texto en archivos con StreamReader'
ms.date: 07/20/2015
helpviewer_keywords:
- files [Visual Basic], writing to
- text, writing to files
- writing to files [Visual Basic], StreamWriter
ms.assetid: 99762e57-ef46-4dcc-8959-a8f79c22f067
ms.openlocfilehash: 373f3bd07ea61263ddd81037d8cbbb06f789e599
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84411582"
---
# <a name="how-to-write-text-to-files-with-a-streamwriter-in-visual-basic"></a><span data-ttu-id="2d323-102">Cómo: Escribir texto en archivos con un objeto StreamWriter en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2d323-102">How to: Write Text to Files with a StreamWriter in Visual Basic</span></span>

<span data-ttu-id="2d323-103">Este ejemplo abre un objeto <xref:System.IO.StreamWriter> con el método `My.Computer.FileSystem.OpenTextFileWriter` y lo usa para escribir una cadena en un archivo de texto con el método <xref:System.IO.TextWriter.WriteLine%2A> de la clase <xref:System.IO.StreamWriter>.</span><span class="sxs-lookup"><span data-stu-id="2d323-103">This example opens a <xref:System.IO.StreamWriter> object with the `My.Computer.FileSystem.OpenTextFileWriter` method and uses it to write a string to a text file with the <xref:System.IO.TextWriter.WriteLine%2A> method of the <xref:System.IO.StreamWriter> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2d323-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2d323-104">Example</span></span>  

 [!code-vb[VbFileIOWrite#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOWrite/VB/Class1.vb#5)]  
  
## <a name="robust-programming"></a><span data-ttu-id="2d323-105">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="2d323-105">Robust Programming</span></span>  

 <span data-ttu-id="2d323-106">Las condiciones siguientes pueden provocar una excepción:</span><span class="sxs-lookup"><span data-stu-id="2d323-106">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="2d323-107">El archivo ya existe y es de solo lectura (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="2d323-107">The file exists and is read-only (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="2d323-108">El disco está lleno (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="2d323-108">The disk is full (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="2d323-109">El nombre de la ruta de acceso es demasiado largo (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="2d323-109">The pathname is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="2d323-110">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="2d323-110">.NET Framework Security</span></span>  

 <span data-ttu-id="2d323-111">En este ejemplo se crea un nuevo archivo, si este no existe aún.</span><span class="sxs-lookup"><span data-stu-id="2d323-111">This example creates a new file, if the file does not already exist.</span></span> <span data-ttu-id="2d323-112">Si una aplicación necesita crear un archivo, precisará acceso `Create` para la carpeta.</span><span class="sxs-lookup"><span data-stu-id="2d323-112">If an application needs to create a file, that application needs `Create` access for the folder.</span></span> <span data-ttu-id="2d323-113">Si el archivo ya existe, la aplicación necesitará solo acceso `Write`, un privilegio menor.</span><span class="sxs-lookup"><span data-stu-id="2d323-113">If the file already exists, the application needs only `Write` access, a lesser privilege.</span></span> <span data-ttu-id="2d323-114">Siempre que sea posible, resulta más seguro crear el archivo durante la implementación y conceder solo acceso `Read` a un único archivo, en lugar de acceso `Create` para una carpeta.</span><span class="sxs-lookup"><span data-stu-id="2d323-114">Where possible, it is more secure to create the file during deployment, and only grant `Read` access to a single file, rather than `Create` access for a folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d323-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="2d323-115">See also</span></span>

- <xref:System.IO.StreamWriter>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileWriter%2A>
- [<span data-ttu-id="2d323-116">Leer de archivos de texto</span><span class="sxs-lookup"><span data-stu-id="2d323-116">How to: Read from Text Files</span></span>](how-to-read-from-text-files.md)
- [<span data-ttu-id="2d323-117">Escritura en archivos</span><span class="sxs-lookup"><span data-stu-id="2d323-117">Writing to Files</span></span>](writing-to-files.md)
