---
title: "Cómo: Proporcionar un cuadro de diálogo de progreso para operaciones de archivos (Guía de programación de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: progress dialog [C#]
ms.assetid: 01b71fe7-8178-4dc8-aeb1-12053be7b51c
caps.latest.revision: "15"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 0ac68b5aa6014db87b4f7a269ef73d0608371bd8
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2017
---
# <a name="how-to-provide-a-progress-dialog-box-for-file-operations-c-programming-guide"></a><span data-ttu-id="294f0-102">Cómo: Proporcionar un cuadro de diálogo de progreso para operaciones de archivos (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="294f0-102">How to: Provide a Progress Dialog Box for File Operations (C# Programming Guide)</span></span>
<span data-ttu-id="294f0-103">Puede proporcionar un cuadro de diálogo estándar que muestra el progreso en las operaciones de archivo en Windows si usa el método <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%28System.String%2CSystem.String%2CMicrosoft.VisualBasic.FileIO.UIOption%29> en el espacio de nombres <xref:Microsoft.VisualBasic?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="294f0-103">You can provide a standard dialog box that shows progress on file operations in Windows if you use the <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%28System.String%2CSystem.String%2CMicrosoft.VisualBasic.FileIO.UIOption%29> method in the <xref:Microsoft.VisualBasic?displayProperty=nameWithType> namespace.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-add-a-reference-in-visual-studio"></a><span data-ttu-id="294f0-104">Para agregar una referencia en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="294f0-104">To add a reference in Visual Studio</span></span>  
  
1.  <span data-ttu-id="294f0-105">En la barra de menús, elija **Proyecto**, **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="294f0-105">On the menu bar, choose **Project**, **Add Reference**.</span></span>  
  
     <span data-ttu-id="294f0-106">Aparecerá el cuadro de diálogo **Administrador de referencias**.</span><span class="sxs-lookup"><span data-stu-id="294f0-106">The **Reference Manager** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="294f0-107">En el área **Ensamblados**, elija **Framework** si no está seleccionado.</span><span class="sxs-lookup"><span data-stu-id="294f0-107">In the **Assemblies** area, choose**Framework** if it isn’t already chosen.</span></span>  
  
3.  <span data-ttu-id="294f0-108">En la lista de nombres, seleccione la casilla **Microsoft.VisualBasic** y elija el botón **Aceptar** para cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="294f0-108">In the list of names, select the **Microsoft.VisualBasic** check box, and then choose the **OK** button to close the dialog box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="294f0-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="294f0-109">Example</span></span>  
 <span data-ttu-id="294f0-110">El siguiente código copia el directorio que especifica `sourcePath` en el directorio que especifica `destinationPath`.</span><span class="sxs-lookup"><span data-stu-id="294f0-110">The following code copies the directory that `sourcePath` specifies into the directory that `destinationPath` specifies.</span></span> <span data-ttu-id="294f0-111">Este código también proporciona un cuadro de diálogo estándar en el que se muestra el tiempo estimado restante antes de que finalice la operación.</span><span class="sxs-lookup"><span data-stu-id="294f0-111">This code also provides a standard dialog box that shows the estimated amount of time remaining before the operation finishes.</span></span>  
  
 [!code-csharp[csFilesandFolders#11](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-provide-a-progress-dialog-box-for-file-operations_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="294f0-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="294f0-112">See Also</span></span>  
 [<span data-ttu-id="294f0-113">Registro y sistema de archivos (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="294f0-113">File System and the Registry (C# Programming Guide)</span></span>](../../../csharp/programming-guide/file-system/index.md)
