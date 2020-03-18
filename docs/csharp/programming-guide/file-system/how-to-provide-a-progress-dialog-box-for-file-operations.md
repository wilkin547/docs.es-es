---
title: 'Procedimiento Proporcionar un cuadro de diálogo de progreso para operaciones de archivos: Guía de programación de C#'
ms.date: 07/20/2015
helpviewer_keywords:
- progress dialog [C#]
ms.assetid: 01b71fe7-8178-4dc8-aeb1-12053be7b51c
ms.openlocfilehash: 30ab84054d26f5b32a3f042a8d35d5ef1211d928
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "75705137"
---
# <a name="how-to-provide-a-progress-dialog-box-for-file-operations-c-programming-guide"></a><span data-ttu-id="3e109-102">Procedimiento Proporcionar un cuadro de diálogo de progreso para operaciones de archivos (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="3e109-102">How to provide a progress dialog box for file operations (C# Programming Guide)</span></span>
<span data-ttu-id="3e109-103">Puede proporcionar un cuadro de diálogo estándar que muestra el progreso en las operaciones de archivo en Windows si usa el método <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%28System.String%2CSystem.String%2CMicrosoft.VisualBasic.FileIO.UIOption%29> en el espacio de nombres <xref:Microsoft.VisualBasic?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3e109-103">You can provide a standard dialog box that shows progress on file operations in Windows if you use the <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%28System.String%2CSystem.String%2CMicrosoft.VisualBasic.FileIO.UIOption%29> method in the <xref:Microsoft.VisualBasic?displayProperty=nameWithType> namespace.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-add-a-reference-in-visual-studio"></a><span data-ttu-id="3e109-104">Para agregar una referencia en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="3e109-104">To add a reference in Visual Studio</span></span>  
  
1. <span data-ttu-id="3e109-105">En la barra de menús, elija **Proyecto**, **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="3e109-105">On the menu bar, choose **Project**, **Add Reference**.</span></span>  
  
     <span data-ttu-id="3e109-106">Aparecerá el cuadro de diálogo **Administrador de referencias**.</span><span class="sxs-lookup"><span data-stu-id="3e109-106">The **Reference Manager** dialog box appears.</span></span>  
  
2. <span data-ttu-id="3e109-107">En el área **Ensamblados**, elija **Framework** si no está ya seleccionado.</span><span class="sxs-lookup"><span data-stu-id="3e109-107">In the **Assemblies** area, choose **Framework** if it isn’t already chosen.</span></span>  
  
3. <span data-ttu-id="3e109-108">En la lista de nombres, seleccione la casilla **Microsoft.VisualBasic** y elija el botón **Aceptar** para cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="3e109-108">In the list of names, select the **Microsoft.VisualBasic** check box, and then choose the **OK** button to close the dialog box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3e109-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3e109-109">Example</span></span>  
 <span data-ttu-id="3e109-110">El siguiente código copia el directorio que especifica `sourcePath` en el directorio que especifica `destinationPath`.</span><span class="sxs-lookup"><span data-stu-id="3e109-110">The following code copies the directory that `sourcePath` specifies into the directory that `destinationPath` specifies.</span></span> <span data-ttu-id="3e109-111">Este código también proporciona un cuadro de diálogo estándar en el que se muestra el tiempo estimado restante antes de que finalice la operación.</span><span class="sxs-lookup"><span data-stu-id="3e109-111">This code also provides a standard dialog box that shows the estimated amount of time remaining before the operation finishes.</span></span>  
  
 [!code-csharp[csFilesandFolders#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#11)]  
  
## <a name="see-also"></a><span data-ttu-id="3e109-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="3e109-112">See also</span></span>

- [<span data-ttu-id="3e109-113">Registro y sistema de archivos (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="3e109-113">File System and the Registry (C# Programming Guide)</span></span>](./index.md)
