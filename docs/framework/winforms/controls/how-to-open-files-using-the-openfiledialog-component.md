---
title: 'Cómo: abrir archivos con el componente OpenFileDialog'
ms.date: 02/11/2019
description: Obtenga información sobre cómo usar el componente OpenFileDialog para abrir el cuadro de diálogo de Windows para examinar y seleccionar archivos.
dev_langs:
- csharp
- vb
helpviewer_keywords:
- OpenFileDialog component [Windows Forms], opening files
- OpenFile method [Windows Forms], OpenFileDialog component
- files [Windows Forms], opening with OpenFileDialog component
ms.assetid: 9d88367a-cc21-4ffd-be74-89fd63767d35
ms.openlocfilehash: d571885011b0f0c723c73a417f294f30f96952f4
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904434"
---
# <a name="how-to-open-files-with-the-openfiledialog"></a><span data-ttu-id="a39dd-103">Cómo: abrir archivos con el método OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="a39dd-103">How to: Open files with the OpenFileDialog</span></span>

<span data-ttu-id="a39dd-104">El <xref:System.Windows.Forms.OpenFileDialog?displayProperty=nameWithType> componente abre el cuadro de diálogo de Windows para examinar y seleccionar archivos.</span><span class="sxs-lookup"><span data-stu-id="a39dd-104">The <xref:System.Windows.Forms.OpenFileDialog?displayProperty=nameWithType> component opens the Windows dialog box for browsing and selecting files.</span></span> <span data-ttu-id="a39dd-105">Para abrir y leer los archivos seleccionados, puede usar el <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A?displayProperty=nameWithType> método o crear una instancia de la <xref:System.IO.StreamReader?displayProperty=nameWithType> clase.</span><span class="sxs-lookup"><span data-stu-id="a39dd-105">To open and read the selected files, you can use the <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A?displayProperty=nameWithType> method, or create an instance of the <xref:System.IO.StreamReader?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="a39dd-106">En los ejemplos siguientes se muestran ambos enfoques.</span><span class="sxs-lookup"><span data-stu-id="a39dd-106">The following examples show both approaches.</span></span>

<span data-ttu-id="a39dd-107">En .NET Framework, para obtener o establecer la <xref:System.Windows.Forms.FileDialog.FileName%2A> propiedad se requiere un nivel de privilegios concedido por la <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> clase.</span><span class="sxs-lookup"><span data-stu-id="a39dd-107">In .NET Framework, to get or set the <xref:System.Windows.Forms.FileDialog.FileName%2A> property requires a privilege level granted by the <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="a39dd-108">Los ejemplos ejecutan una <xref:System.Security.Permissions.FileIOPermission> comprobación de permisos y pueden producir una excepción debido a privilegios insuficientes si se ejecutan en un contexto de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="a39dd-108">The examples run a <xref:System.Security.Permissions.FileIOPermission> permission check, and can throw an exception due to insufficient privileges if run in a partial-trust context.</span></span> <span data-ttu-id="a39dd-109">Para obtener más información, vea [conceptos básicos](../../misc/code-access-security-basics.md)de la seguridad de acceso del código.</span><span class="sxs-lookup"><span data-stu-id="a39dd-109">For more information, see [Code access security basics](../../misc/code-access-security-basics.md).</span></span>

<span data-ttu-id="a39dd-110">Puede compilar y ejecutar estos ejemplos como aplicaciones .NET Framework desde la línea de comandos de C# o Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="a39dd-110">You can build and run these examples as .NET Framework apps from the C# or Visual Basic command line.</span></span> <span data-ttu-id="a39dd-111">Para obtener más información, vea [compilar mediante línea de comandos con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) o [compilar desde la línea de comandos](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).</span><span class="sxs-lookup"><span data-stu-id="a39dd-111">For more information, see [Command-line building with csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) or [Build from the command line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).</span></span>

<span data-ttu-id="a39dd-112">A partir de .NET Core 3,0, también puede compilar y ejecutar los ejemplos como aplicaciones Windows .NET Core desde una carpeta que tiene un archivo de proyecto Windows Forms \* \<folder name> . csproj\* de .net Core.</span><span class="sxs-lookup"><span data-stu-id="a39dd-112">Starting with .NET Core 3.0, you can also build and run the examples as Windows .NET Core apps from a folder that has a .NET Core Windows Forms *\<folder name>.csproj* project file.</span></span>

## <a name="example-read-a-file-as-a-stream-with-streamreader"></a><span data-ttu-id="a39dd-113">Ejemplo: leer un archivo como una secuencia con StreamReader</span><span class="sxs-lookup"><span data-stu-id="a39dd-113">Example: Read a file as a stream with StreamReader</span></span>  
  
<span data-ttu-id="a39dd-114">En el ejemplo siguiente se usa el <xref:System.Windows.Forms.Button> controlador de eventos del control Windows Forms <xref:System.Windows.Forms.Control.Click> para abrir <xref:System.Windows.Forms.OpenFileDialog> con el <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> método.</span><span class="sxs-lookup"><span data-stu-id="a39dd-114">The following example uses the Windows Forms <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler to open the <xref:System.Windows.Forms.OpenFileDialog> with the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span> <span data-ttu-id="a39dd-115">Una vez que el usuario elige un archivo y selecciona **Aceptar**, una instancia de la <xref:System.IO.StreamReader> clase lee el archivo y muestra su contenido en el cuadro de texto del formulario.</span><span class="sxs-lookup"><span data-stu-id="a39dd-115">After the user chooses a file and selects **OK**, an instance of the <xref:System.IO.StreamReader> class reads the file and displays its contents in the form's text box.</span></span> <span data-ttu-id="a39dd-116">Para obtener más información acerca de la lectura de secuencias de archivos, vea <xref:System.IO.FileStream.BeginRead%2A?displayProperty=nameWithType> y <xref:System.IO.FileStream.Read%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="a39dd-116">For more information about reading from file streams, see <xref:System.IO.FileStream.BeginRead%2A?displayProperty=nameWithType> and <xref:System.IO.FileStream.Read%2A?displayProperty=nameWithType>.</span></span>  

 [!code-csharp[OpenFileDialog#1](~/samples/snippets/winforms/open-files/example1/cs/Form1.cs)]
 [!code-vb[OpenFileDialog#1](~/samples/snippets/winforms/open-files/example1/vb/Form1.vb)]  

## <a name="example-open-a-file-from-a-filtered-selection-with-openfile"></a><span data-ttu-id="a39dd-117">Ejemplo: abrir un archivo de una selección filtrada con OpenFile</span><span class="sxs-lookup"><span data-stu-id="a39dd-117">Example: Open a file from a filtered selection with OpenFile</span></span>

<span data-ttu-id="a39dd-118">En el ejemplo siguiente se usa el <xref:System.Windows.Forms.Button> controlador de eventos del control <xref:System.Windows.Forms.Control.Click> para abrir el <xref:System.Windows.Forms.OpenFileDialog> con un filtro que muestra solo archivos de texto.</span><span class="sxs-lookup"><span data-stu-id="a39dd-118">The following example uses the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler to open the <xref:System.Windows.Forms.OpenFileDialog> with a filter that shows only text files.</span></span> <span data-ttu-id="a39dd-119">Una vez que el usuario elige un archivo de texto y selecciona **Aceptar**, el <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> método se usa para abrir el archivo en el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="a39dd-119">After the user chooses a text file and selects **OK**, the <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> method is used to open the file in Notepad.</span></span>

 [!code-csharp[OpenFileDialog#2](~/samples/snippets/winforms/open-files/example2/cs/Form1.cs)]
 [!code-vb[OpenFileDialog#2](~/samples/snippets/winforms/open-files/example2/vb/Form1.vb)]  

## <a name="see-also"></a><span data-ttu-id="a39dd-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a39dd-120">See also</span></span>

- <xref:System.Windows.Forms.OpenFileDialog>
- [<span data-ttu-id="a39dd-121">OpenFileDialog (componente)</span><span class="sxs-lookup"><span data-stu-id="a39dd-121">OpenFileDialog component</span></span>](openfiledialog-component-windows-forms.md)
