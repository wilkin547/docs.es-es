---
title: "Solución de problemas: Leer y escribir en archivos de texto (Visual Basic)"
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
- troubleshooting file I/O
- writing text to files, troubleshooting
- troubleshooting Visual Basic, text files
- I/O [Visual Basic], troubleshooting text files
- writing to files, troubleshooting
- reading text files, troubleshooting
ms.assetid: a8e9b44d-facb-4718-8c0f-466537171182
caps.latest.revision: 10
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
ms.openlocfilehash: 7f1d26df53445ee9711ebb2840071d2560c5380d
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="troubleshooting-reading-from-and-writing-to-text-files-visual-basic"></a><span data-ttu-id="aa3fd-102">Solución de problemas: Leer y escribir en archivos de texto (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="aa3fd-102">Troubleshooting: reading from and writing to text files (Visual Basic)</span></span>
<span data-ttu-id="aa3fd-103">En este tema se tratan problemas habituales que surgen cuando se trabaja con archivos de texto y se sugiere un enfoque para cada uno.</span><span class="sxs-lookup"><span data-stu-id="aa3fd-103">This topic discusses common problems encountered when working with text files and suggests an approach to each.</span></span>  
  
## <a name="common-problems"></a><span data-ttu-id="aa3fd-104">Problemas habituales</span><span class="sxs-lookup"><span data-stu-id="aa3fd-104">Common problems</span></span>  
 <span data-ttu-id="aa3fd-105">Entre los problemas más frecuentes que se producen al trabajar con archivos de texto se incluyen excepciones de seguridad, codificaciones de archivos o rutas de acceso no válidas.</span><span class="sxs-lookup"><span data-stu-id="aa3fd-105">The most common issues encountered when working with text files include security exceptions, file encodings, or invalid paths.</span></span>  
  
### <a name="security-exceptions"></a><span data-ttu-id="aa3fd-106">Excepciones de seguridad</span><span class="sxs-lookup"><span data-stu-id="aa3fd-106">Security exceptions</span></span>  
 <span data-ttu-id="aa3fd-107">Se genera <xref:System.Security.SecurityException> cuando se produce un error de seguridad.</span><span class="sxs-lookup"><span data-stu-id="aa3fd-107">A <xref:System.Security.SecurityException> is thrown when a security error occurs.</span></span> <span data-ttu-id="aa3fd-108">Suele ser consecuencia de que el usuario carezca de los permisos necesarios, lo que se puede resolver al agregar permisos o trabajar con archivos en almacenamiento aislado.</span><span class="sxs-lookup"><span data-stu-id="aa3fd-108">This is often a result of the user lacking necessary permissions, which may be solved by adding permissions or working with files in isolated storage.</span></span>  
  
### <a name="file-encodings"></a><span data-ttu-id="aa3fd-109">Codificaciones de archivos</span><span class="sxs-lookup"><span data-stu-id="aa3fd-109">File encodings</span></span>  
 <span data-ttu-id="aa3fd-110">Las codificaciones de archivos, también denominadas codificaciones de caracteres, especifican cómo se representan los caracteres durante el procesamiento de texto.</span><span class="sxs-lookup"><span data-stu-id="aa3fd-110">File encodings, also known as character encodings, specify how to represent characters when text processing.</span></span> <span data-ttu-id="aa3fd-111">La presencia de caracteres inesperados en un archivo de texto puede deberse a una codificación incorrecta.</span><span class="sxs-lookup"><span data-stu-id="aa3fd-111">Unexpected characters in a text file may result from incorrect encoding.</span></span> <span data-ttu-id="aa3fd-112">Con la mayoría de los archivos, puede que una codificación sea preferible a otra en función de los caracteres del lenguaje que pueda controlar, aunque normalmente se prefiere Unicode.</span><span class="sxs-lookup"><span data-stu-id="aa3fd-112">For most files, one encoding may be preferable over another in terms of which language characters it can or cannot handle, although Unicode is usually preferred.</span></span> <span data-ttu-id="aa3fd-113">Para más información, vea [Codificación de archivos](../../../../visual-basic/developing-apps/programming/drives-directories-files/file-encodings.md) y <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="aa3fd-113">For more information, see [File Encodings](../../../../visual-basic/developing-apps/programming/drives-directories-files/file-encodings.md) and <xref:System.Text.Encoding>.</span></span>  
  
### <a name="incorrect-paths"></a><span data-ttu-id="aa3fd-114">Rutas de acceso incorrectas</span><span class="sxs-lookup"><span data-stu-id="aa3fd-114">Incorrect paths</span></span>  
 <span data-ttu-id="aa3fd-115">Al analizar rutas de acceso de archivo, sobre todo rutas de acceso relativas, es fácil especificar datos equivocados.</span><span class="sxs-lookup"><span data-stu-id="aa3fd-115">When parsing file paths, particularly relative paths, it is easy to supply the wrong data.</span></span> <span data-ttu-id="aa3fd-116">Muchos problemas pueden corregirse asegurándose de que especifica la ruta de acceso correcta.</span><span class="sxs-lookup"><span data-stu-id="aa3fd-116">Many problems can be corrected by making sure you are supplying the correct path.</span></span> <span data-ttu-id="aa3fd-117">Para obtener más información, vea [How to: Parse File Paths in Visual Basic](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md) (Cómo: Analizar rutas de acceso a archivos en Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="aa3fd-117">For more information, see [How to: Parse File Paths](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa3fd-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="aa3fd-118">See also</span></span>  
 <span data-ttu-id="aa3fd-119"><xref:Microsoft.VisualBasic.FileIO.FileSystem></span><span class="sxs-lookup"><span data-stu-id="aa3fd-119"><xref:Microsoft.VisualBasic.FileIO.FileSystem></span></span>   
 <span data-ttu-id="aa3fd-120">[Reading from Files in Visual Basic](../../../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)  (Leer archivos en Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="aa3fd-120">[Reading from Files](../../../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md) </span></span>  
 <span data-ttu-id="aa3fd-121">[Writing to Files](../../../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md)  (Escribir en archivos en Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="aa3fd-121">[Writing to Files](../../../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md) </span></span>  
 [<span data-ttu-id="aa3fd-122">Análisis de archivos de texto con el objeto TextFieldParser</span><span class="sxs-lookup"><span data-stu-id="aa3fd-122">Parsing Text Files with the TextFieldParser Object</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)

