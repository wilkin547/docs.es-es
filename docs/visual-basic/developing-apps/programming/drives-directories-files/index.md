---
title: Procesar unidades, directorios y archivos (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- drives
- drives, processing
- Visual Basic code, file access
- files [Visual Basic], processing
- files [Visual Basic], accessing
- directories [Visual Studio], processing
ms.assetid: f1db14c8-a4fd-4d0b-8323-c7cb29d688c2
ms.openlocfilehash: 0c9c1c787138595f725316a580acda9c5d4d43a9
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "43863629"
---
# <a name="processing-drives-directories-and-files-visual-basic"></a><span data-ttu-id="50f05-102">Procesar unidades, directorios y archivos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="50f05-102">Processing Drives, Directories, and Files (Visual Basic)</span></span>
<span data-ttu-id="50f05-103">Se puede usar Visual Basic para procesar unidades, carpetas y archivos con el objeto `My.Computer.FileSystem`, que proporciona un mejor rendimiento y es más fácil de usar que los métodos tradicionales como las funciones `FileOpen` y `Write` (aunque siguen estando disponibles).</span><span class="sxs-lookup"><span data-stu-id="50f05-103">You can use Visual Basic to process drives, folders, and files with the `My.Computer.FileSystem` object, which provides better performance and is easier to use than traditional methods such as the `FileOpen` and `Write` functions (although they are still available).</span></span> <span data-ttu-id="50f05-104">En las secciones siguientes se describen estos métodos con detalle.</span><span class="sxs-lookup"><span data-stu-id="50f05-104">The following sections discuss these methods in detail.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="50f05-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="50f05-105">In This Section</span></span>  
 [<span data-ttu-id="50f05-106">Acceso a archivos con Visual Basic</span><span class="sxs-lookup"><span data-stu-id="50f05-106">File Access with Visual Basic</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/file-access.md)  
 <span data-ttu-id="50f05-107">Describe cómo usar el objeto `My.Computer.FileSystem` para trabajar con archivos, unidades y carpetas.</span><span class="sxs-lookup"><span data-stu-id="50f05-107">Discusses how to use the `My.Computer.FileSystem` object to work with files, drives, and folders.</span></span>  
  
 [<span data-ttu-id="50f05-108">Fundamentos del sistema de archivos y la E/S de archivos en .NET Framework (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="50f05-108">Basics of .NET Framework File I/O and the File System (Visual Basic)</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/basics-of-net-framework-file-io-and-the-file-system.md)  
 <span data-ttu-id="50f05-109">Proporciona una visión general de los conceptos de E/S de archivos en .NET Framework, incluidas las secuencias, el almacenamiento aislado, eventos de archivo, atributos de archivo y acceso a archivos.</span><span class="sxs-lookup"><span data-stu-id="50f05-109">Provides an overview of file I/O concepts in the .NET Framework, including streams, isolated storage, file events, file attributes, and file access.</span></span>  
  
 [<span data-ttu-id="50f05-110">Tutorial: Manipulación de archivos utilizando métodos de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="50f05-110">Walkthrough: Manipulating Files by Using .NET Framework Methods</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-by-using-net-framework-methods.md)  
 <span data-ttu-id="50f05-111">Muestra cómo usar [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] para manipular archivos y carpetas.</span><span class="sxs-lookup"><span data-stu-id="50f05-111">Demonstrates how to use the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] to manipulate files and folders.</span></span>  
  
 [<span data-ttu-id="50f05-112">Tutorial: Manipulación de archivos y directorios en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="50f05-112">Walkthrough: Manipulating Files and Directories in Visual Basic</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-and-directories.md)  
 <span data-ttu-id="50f05-113">Muestra cómo usar el objeto `My.Computer.FileSystem` para manipular archivos y carpetas.</span><span class="sxs-lookup"><span data-stu-id="50f05-113">Demonstrates how to use the `My.Computer.FileSystem` object to manipulate files and folders.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="50f05-114">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="50f05-114">Related Sections</span></span>  
 [<span data-ttu-id="50f05-115">Convenciones de código y estructura de programas</span><span class="sxs-lookup"><span data-stu-id="50f05-115">Program Structure and Code Conventions</span></span>](../../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)  
 <span data-ttu-id="50f05-116">Proporciona instrucciones para la estructura física y la apariencia de los programas.</span><span class="sxs-lookup"><span data-stu-id="50f05-116">Provides guidelines for the physical structure and appearance of programs.</span></span>  
  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem>  
 <span data-ttu-id="50f05-117">Documentación de referencia para el objeto `My.Computer.FileSystem` y sus miembros.</span><span class="sxs-lookup"><span data-stu-id="50f05-117">Reference documentation for the `My.Computer.FileSystem` object and its members.</span></span>
