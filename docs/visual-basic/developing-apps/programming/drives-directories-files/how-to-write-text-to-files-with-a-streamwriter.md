---
title: "Cómo: Escribir texto en archivos con un objeto StreamWriter en Visual Basic"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- files, writing to
- text, writing to files
- writing to files, StreamWriter
ms.assetid: 99762e57-ef46-4dcc-8959-a8f79c22f067
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: ea85d57e9af4fdd640733db5dc2fa8b0ab25325c
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-write-text-to-files-with-a-streamwriter-in-visual-basic"></a><span data-ttu-id="7529b-102">Cómo: Escribir texto en archivos con un objeto StreamWriter en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7529b-102">How to: Write Text to Files with a StreamWriter in Visual Basic</span></span>
<span data-ttu-id="7529b-103">Este ejemplo abre un objeto <xref:System.IO.StreamWriter> con el método `My.Computer.FileSystem.OpenTextFileWriter` y lo usa para escribir una cadena en un archivo de texto con el método <xref:System.IO.TextWriter.WriteLine%2A> de la clase <xref:System.IO.StreamWriter>.</span><span class="sxs-lookup"><span data-stu-id="7529b-103">This example opens a <xref:System.IO.StreamWriter> object with the `My.Computer.FileSystem.OpenTextFileWriter` method and uses it to write a string to a text file with the <xref:System.IO.TextWriter.WriteLine%2A> method of the <xref:System.IO.StreamWriter> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7529b-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7529b-104">Example</span></span>  
 <span data-ttu-id="7529b-105">[!code-vb[VbFileIOWrite#5](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-text-to-files-with-a-streamwriter_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="7529b-105">[!code-vb[VbFileIOWrite#5](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-text-to-files-with-a-streamwriter_1.vb)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="7529b-106">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="7529b-106">Robust Programming</span></span>  
 <span data-ttu-id="7529b-107">Las condiciones siguientes pueden provocar una excepción:</span><span class="sxs-lookup"><span data-stu-id="7529b-107">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="7529b-108">El archivo ya existe y es de solo lectura (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="7529b-108">The file exists and is read-only (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="7529b-109">El disco está lleno (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="7529b-109">The disk is full (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="7529b-110">El nombre de la ruta de acceso es demasiado largo (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="7529b-110">The pathname is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="7529b-111">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="7529b-111">.NET Framework Security</span></span>  
 <span data-ttu-id="7529b-112">En este ejemplo se crea un nuevo archivo, si este no existe aún.</span><span class="sxs-lookup"><span data-stu-id="7529b-112">This example creates a new file, if the file does not already exist.</span></span> <span data-ttu-id="7529b-113">Si una aplicación necesita crear un archivo, precisará acceso `Create` para la carpeta.</span><span class="sxs-lookup"><span data-stu-id="7529b-113">If an application needs to create a file, that application needs `Create` access for the folder.</span></span> <span data-ttu-id="7529b-114">Si el archivo ya existe, la aplicación necesitará solo acceso `Write`, un privilegio menor.</span><span class="sxs-lookup"><span data-stu-id="7529b-114">If the file already exists, the application needs only `Write` access, a lesser privilege.</span></span> <span data-ttu-id="7529b-115">Siempre que sea posible, resulta más seguro crear el archivo durante la implementación y conceder solo acceso `Read` a un único archivo, en lugar de acceso `Create` para una carpeta.</span><span class="sxs-lookup"><span data-stu-id="7529b-115">Where possible, it is more secure to create the file during deployment, and only grant `Read` access to a single file, rather than `Create` access for a folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7529b-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="7529b-116">See Also</span></span>  
 <span data-ttu-id="7529b-117"><xref:System.IO.StreamWriter></span><span class="sxs-lookup"><span data-stu-id="7529b-117"><xref:System.IO.StreamWriter></span></span>   
 <span data-ttu-id="7529b-118"><xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileWriter%2A></span><span class="sxs-lookup"><span data-stu-id="7529b-118"><xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileWriter%2A></span></span>   
 <span data-ttu-id="7529b-119">[Cómo: Leer archivos de texto en Visual Basic](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files.md) </span><span class="sxs-lookup"><span data-stu-id="7529b-119">[How to: Read from Text Files](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files.md) </span></span>  
 [<span data-ttu-id="7529b-120">Escritura en archivos</span><span class="sxs-lookup"><span data-stu-id="7529b-120">Writing to Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md)

