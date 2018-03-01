---
title: "Cómo: Recuperar el contenido del directorio Mis documentos en Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- My Documents directory
ms.assetid: 26560d01-7dda-4457-8e95-21db23d71aea
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3456984a697439a8c2ab7fb88f9f0f32d10cb0e7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-retrieve-the-contents-of-the-my-documents-directory-in-visual-basic"></a><span data-ttu-id="a8886-102">Cómo: Recuperar el contenido del directorio Mis documentos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a8886-102">How to: Retrieve the Contents of the My Documents Directory in Visual Basic</span></span>
<span data-ttu-id="a8886-103">El objeto <xref:Microsoft.VisualBasic.FileIO.SpecialDirectories> se puede usar para leer en muchos de los directorios de **Todos los usuarios**, como **Mis documentos** o **Escritorio**.</span><span class="sxs-lookup"><span data-stu-id="a8886-103">The <xref:Microsoft.VisualBasic.FileIO.SpecialDirectories> object can be used to read from many of the **All Users** directories, such as **My Documents** or **Desktop**.</span></span>  
  
### <a name="to-read-from-the-my-documents-folder"></a><span data-ttu-id="a8886-104">Para leer de la carpeta Mis documentos</span><span class="sxs-lookup"><span data-stu-id="a8886-104">To read from the My Documents folder</span></span>  
  
-   <span data-ttu-id="a8886-105">Use el método `ReadAllText` para leer el texto de cada archivo situado en un directorio concreto.</span><span class="sxs-lookup"><span data-stu-id="a8886-105">Use the `ReadAllText` method to read the text from each file in a specific directory.</span></span> <span data-ttu-id="a8886-106">El código siguiente especifica un directorio y un archivo y, después, usa `ReadAllText` para leerlos en la cadena denominada `patients`.</span><span class="sxs-lookup"><span data-stu-id="a8886-106">The following code specifies a directory and file and then uses `ReadAllText` to read them into the string named `patients`.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#15](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-retrieve-the-contents-of-the-my-documents-directory_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="a8886-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="a8886-107">See Also</span></span>  
 <xref:Microsoft.VisualBasic.FileIO.SpecialDirectories>  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllText%2A>
