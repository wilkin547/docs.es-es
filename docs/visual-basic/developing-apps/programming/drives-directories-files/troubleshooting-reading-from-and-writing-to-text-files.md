---
title: 'Solución de problemas: Leer y escribir en archivos de texto'
ms.date: 07/20/2015
helpviewer_keywords:
- troubleshooting file I/O
- writing text to files [Visual Basic], troubleshooting
- troubleshooting Visual Basic, text files
- I/O [Visual Basic], troubleshooting text files
- writing to files [Visual Basic], troubleshooting
- reading text files [Visual Basic], troubleshooting
ms.assetid: a8e9b44d-facb-4718-8c0f-466537171182
ms.openlocfilehash: dbc53ca3cc9ae9b2d14b925f891d0409b2b7debd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "74333796"
---
# <a name="troubleshooting-reading-from-and-writing-to-text-files-visual-basic"></a><span data-ttu-id="060b4-102">Solución de problemas: Leer y escribir en archivos de texto (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="060b4-102">Troubleshooting: reading from and writing to text files (Visual Basic)</span></span>

<span data-ttu-id="060b4-103">En este tema se tratan problemas habituales que surgen cuando se trabaja con archivos de texto y se sugiere un enfoque para cada uno.</span><span class="sxs-lookup"><span data-stu-id="060b4-103">This topic discusses common problems encountered when working with text files and suggests an approach to each.</span></span>  
  
## <a name="common-problems"></a><span data-ttu-id="060b4-104">Problemas habituales</span><span class="sxs-lookup"><span data-stu-id="060b4-104">Common problems</span></span>  

 <span data-ttu-id="060b4-105">Entre los problemas más frecuentes que se producen al trabajar con archivos de texto se incluyen excepciones de seguridad, codificaciones de archivos o rutas de acceso no válidas.</span><span class="sxs-lookup"><span data-stu-id="060b4-105">The most common issues encountered when working with text files include security exceptions, file encodings, or invalid paths.</span></span>  
  
### <a name="security-exceptions"></a><span data-ttu-id="060b4-106">Excepciones de seguridad</span><span class="sxs-lookup"><span data-stu-id="060b4-106">Security exceptions</span></span>  

 <span data-ttu-id="060b4-107">Se genera <xref:System.Security.SecurityException> cuando se produce un error de seguridad.</span><span class="sxs-lookup"><span data-stu-id="060b4-107">A <xref:System.Security.SecurityException> is thrown when a security error occurs.</span></span> <span data-ttu-id="060b4-108">Suele ser consecuencia de que el usuario carezca de los permisos necesarios, lo que se puede resolver al agregar permisos o trabajar con archivos en almacenamiento aislado.</span><span class="sxs-lookup"><span data-stu-id="060b4-108">This is often a result of the user lacking necessary permissions, which may be solved by adding permissions or working with files in isolated storage.</span></span>  
  
### <a name="file-encodings"></a><span data-ttu-id="060b4-109">Codificaciones de archivos</span><span class="sxs-lookup"><span data-stu-id="060b4-109">File encodings</span></span>  

 <span data-ttu-id="060b4-110">Las codificaciones de archivos, también denominadas codificaciones de caracteres, especifican cómo se representan los caracteres durante el procesamiento de texto.</span><span class="sxs-lookup"><span data-stu-id="060b4-110">File encodings, also known as character encodings, specify how to represent characters when text processing.</span></span> <span data-ttu-id="060b4-111">La presencia de caracteres inesperados en un archivo de texto puede deberse a una codificación incorrecta.</span><span class="sxs-lookup"><span data-stu-id="060b4-111">Unexpected characters in a text file may result from incorrect encoding.</span></span> <span data-ttu-id="060b4-112">Con la mayoría de los archivos, puede que una codificación sea preferible a otra en función de los caracteres del lenguaje que pueda controlar, aunque normalmente se prefiere Unicode.</span><span class="sxs-lookup"><span data-stu-id="060b4-112">For most files, one encoding may be preferable over another in terms of which language characters it can or cannot handle, although Unicode is usually preferred.</span></span> <span data-ttu-id="060b4-113">Para más información, vea [Codificación de archivos](../../../../visual-basic/developing-apps/programming/drives-directories-files/file-encodings.md) y <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="060b4-113">For more information, see [File Encodings](../../../../visual-basic/developing-apps/programming/drives-directories-files/file-encodings.md) and <xref:System.Text.Encoding>.</span></span>  
  
### <a name="incorrect-paths"></a><span data-ttu-id="060b4-114">Rutas de acceso incorrectas</span><span class="sxs-lookup"><span data-stu-id="060b4-114">Incorrect paths</span></span>  

 <span data-ttu-id="060b4-115">Al analizar rutas de acceso de archivo, sobre todo rutas de acceso relativas, es fácil especificar datos equivocados.</span><span class="sxs-lookup"><span data-stu-id="060b4-115">When parsing file paths, particularly relative paths, it is easy to supply the wrong data.</span></span> <span data-ttu-id="060b4-116">Muchos problemas pueden corregirse asegurándose de que especifica la ruta de acceso correcta.</span><span class="sxs-lookup"><span data-stu-id="060b4-116">Many problems can be corrected by making sure you are supplying the correct path.</span></span> <span data-ttu-id="060b4-117">Para obtener más información, vea [How to: Parse File Paths in Visual Basic](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md) (Cómo: Analizar rutas de acceso a archivos en Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="060b4-117">For more information, see [How to: Parse File Paths](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="060b4-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="060b4-118">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- [<span data-ttu-id="060b4-119">Leer archivos</span><span class="sxs-lookup"><span data-stu-id="060b4-119">Reading from Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)
- [<span data-ttu-id="060b4-120">Escritura en archivos</span><span class="sxs-lookup"><span data-stu-id="060b4-120">Writing to Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md)
- [<span data-ttu-id="060b4-121">Análisis de archivos de texto con el objeto TextFieldParser</span><span class="sxs-lookup"><span data-stu-id="060b4-121">Parsing Text Files with the TextFieldParser Object</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)
