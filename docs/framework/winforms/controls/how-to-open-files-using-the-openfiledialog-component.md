---
title: 'Cómo: Abrir archivos con el componente OpenFileDialog'
ms.date: 02/11/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- OpenFileDialog component [Windows Forms], opening files
- OpenFile method [Windows Forms], OpenFileDialog component
- files [Windows Forms], opening with OpenFileDialog component
ms.assetid: 9d88367a-cc21-4ffd-be74-89fd63767d35
ms.openlocfilehash: ca69de19ab1b9ae387002898145fe99e35a7b6b9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182132"
---
# <a name="how-to-open-files-with-the-openfiledialog"></a><span data-ttu-id="6e971-102">Cómo: Abrir archivos con OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="6e971-102">How to: Open files with the OpenFileDialog</span></span>

<span data-ttu-id="6e971-103">El <xref:System.Windows.Forms.OpenFileDialog?displayProperty=nameWithType> componente abre el cuadro de diálogo de Windows para examinar y seleccionar archivos.</span><span class="sxs-lookup"><span data-stu-id="6e971-103">The <xref:System.Windows.Forms.OpenFileDialog?displayProperty=nameWithType> component opens the Windows dialog box for browsing and selecting files.</span></span> <span data-ttu-id="6e971-104">Para abrir y leer los archivos <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A?displayProperty=nameWithType> seleccionados, puede utilizar <xref:System.IO.StreamReader?displayProperty=nameWithType> el método o crear una instancia de la clase.</span><span class="sxs-lookup"><span data-stu-id="6e971-104">To open and read the selected files, you can use the <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A?displayProperty=nameWithType> method, or create an instance of the <xref:System.IO.StreamReader?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="6e971-105">En los ejemplos siguientes se muestran ambos enfoques.</span><span class="sxs-lookup"><span data-stu-id="6e971-105">The following examples show both approaches.</span></span>

<span data-ttu-id="6e971-106">En .NET Framework, para <xref:System.Windows.Forms.FileDialog.FileName%2A> obtener o establecer la propiedad <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> se requiere un nivel de privilegio concedido por la clase.</span><span class="sxs-lookup"><span data-stu-id="6e971-106">In .NET Framework, to get or set the <xref:System.Windows.Forms.FileDialog.FileName%2A> property requires a privilege level granted by the <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="6e971-107">Los ejemplos <xref:System.Security.Permissions.FileIOPermission> ejecutan una comprobación de permisos y pueden producir una excepción debido a privilegios insuficientes si se ejecutan en un contexto de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="6e971-107">The examples run a <xref:System.Security.Permissions.FileIOPermission> permission check, and can throw an exception due to insufficient privileges if run in a partial-trust context.</span></span> <span data-ttu-id="6e971-108">Para obtener más información, consulte [Conceptos básicos](../../misc/code-access-security-basics.md)de seguridad de acceso a código .</span><span class="sxs-lookup"><span data-stu-id="6e971-108">For more information, see [Code access security basics](../../misc/code-access-security-basics.md).</span></span>

<span data-ttu-id="6e971-109">Puede compilar y ejecutar estos ejemplos como aplicaciones de .NET Framework desde la línea de comandos de Visual Basic o de C.</span><span class="sxs-lookup"><span data-stu-id="6e971-109">You can build and run these examples as .NET Framework apps from the C# or Visual Basic command line.</span></span> <span data-ttu-id="6e971-110">Para obtener más información, vea [Creación de línea de comandos con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) o Compilación desde la línea de [comandos](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).</span><span class="sxs-lookup"><span data-stu-id="6e971-110">For more information, see [Command-line building with csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) or [Build from the command line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).</span></span>

<span data-ttu-id="6e971-111">A partir de .NET Core 3.0, también puede compilar y ejecutar los ejemplos como aplicaciones de Windows .NET Core desde una carpeta que tiene un nombre de \* \<carpeta\* de formularios Windows Forms de .NET Core> archivo de proyecto.csproj.</span><span class="sxs-lookup"><span data-stu-id="6e971-111">Starting with .NET Core 3.0, you can also build and run the examples as Windows .NET Core apps from a folder that has a .NET Core Windows Forms *\<folder name>.csproj* project file.</span></span>

## <a name="example-read-a-file-as-a-stream-with-streamreader"></a><span data-ttu-id="6e971-112">Ejemplo: Leer un archivo como una secuencia con StreamReader</span><span class="sxs-lookup"><span data-stu-id="6e971-112">Example: Read a file as a stream with StreamReader</span></span>  
  
<span data-ttu-id="6e971-113">En <xref:System.Windows.Forms.Button> el <xref:System.Windows.Forms.Control.Click> <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> ejemplo siguiente se usa el controlador <xref:System.Windows.Forms.OpenFileDialog> de eventos del control de formularios Windows Forms para abrir el método.</span><span class="sxs-lookup"><span data-stu-id="6e971-113">The following example uses the Windows Forms <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler to open the <xref:System.Windows.Forms.OpenFileDialog> with the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span> <span data-ttu-id="6e971-114">Después de que el usuario **OK**elige un archivo <xref:System.IO.StreamReader> y selecciona Aceptar , una instancia de la clase lee el archivo y muestra su contenido en el cuadro de texto del formulario.</span><span class="sxs-lookup"><span data-stu-id="6e971-114">After the user chooses a file and selects **OK**, an instance of the <xref:System.IO.StreamReader> class reads the file and displays its contents in the form's text box.</span></span> <span data-ttu-id="6e971-115">Para obtener más información acerca de <xref:System.IO.FileStream.BeginRead%2A?displayProperty=nameWithType> <xref:System.IO.FileStream.Read%2A?displayProperty=nameWithType>la lectura de secuencias de archivos, consulte y .</span><span class="sxs-lookup"><span data-stu-id="6e971-115">For more information about reading from file streams, see <xref:System.IO.FileStream.BeginRead%2A?displayProperty=nameWithType> and <xref:System.IO.FileStream.Read%2A?displayProperty=nameWithType>.</span></span>  

 [!code-csharp[OpenFileDialog#1](~/samples/snippets/winforms/open-files/example1/cs/Form1.cs)]
 [!code-vb[OpenFileDialog#1](~/samples/snippets/winforms/open-files/example1/vb/Form1.vb)]  

## <a name="example-open-a-file-from-a-filtered-selection-with-openfile"></a><span data-ttu-id="6e971-116">Ejemplo: Abra un archivo desde una selección filtrada con OpenFile</span><span class="sxs-lookup"><span data-stu-id="6e971-116">Example: Open a file from a filtered selection with OpenFile</span></span>

<span data-ttu-id="6e971-117">En el ejemplo <xref:System.Windows.Forms.Button> siguiente <xref:System.Windows.Forms.Control.Click> se usa el <xref:System.Windows.Forms.OpenFileDialog> controlador de eventos del control para abrir el con un filtro que muestra solo los archivos de texto.</span><span class="sxs-lookup"><span data-stu-id="6e971-117">The following example uses the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler to open the <xref:System.Windows.Forms.OpenFileDialog> with a filter that shows only text files.</span></span> <span data-ttu-id="6e971-118">Después de que el usuario **OK**elige un <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> archivo de texto y selecciona Aceptar , el método se utiliza para abrir el archivo en el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="6e971-118">After the user chooses a text file and selects **OK**, the <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> method is used to open the file in Notepad.</span></span>

 [!code-csharp[OpenFileDialog#2](~/samples/snippets/winforms/open-files/example2/cs/Form1.cs)]
 [!code-vb[OpenFileDialog#2](~/samples/snippets/winforms/open-files/example2/vb/Form1.vb)]  

## <a name="see-also"></a><span data-ttu-id="6e971-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6e971-119">See also</span></span>

- <xref:System.Windows.Forms.OpenFileDialog>
- [<span data-ttu-id="6e971-120">Componente OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="6e971-120">OpenFileDialog component</span></span>](openfiledialog-component-windows-forms.md)
