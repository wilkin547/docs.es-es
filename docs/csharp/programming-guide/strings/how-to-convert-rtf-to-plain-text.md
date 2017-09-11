---
title: "Cómo: Convertir RTF en texto sin formato (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- strings [C#], converting from RTF
ms.assetid: 3b386a87-899d-4d98-bc82-a980526ddaac
caps.latest.revision: 21
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 9e4c7b48467f3b260526c604fa3a36fc5d80374e
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-convert-rtf-to-plain-text-c-programming-guide"></a><span data-ttu-id="7b05c-102">Cómo: Convertir RTF en texto sin formato (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="7b05c-102">How to: Convert RTF to Plain Text (C# Programming Guide)</span></span>
<span data-ttu-id="7b05c-103">Formato de texto enriquecido (RTF) es un formato de documento desarrollado por Microsoft a finales de los años 80 para permitir el intercambio de documentos en sistemas operativos.</span><span class="sxs-lookup"><span data-stu-id="7b05c-103">Rich Text Format (RTF) is a document format developed by Microsoft in the late 1980s to enable the exchange of documents across operating systems.</span></span> <span data-ttu-id="7b05c-104">Microsoft Word y WordPad pueden leer y escribir documentos RTF.</span><span class="sxs-lookup"><span data-stu-id="7b05c-104">Both Microsoft Word and WordPad can read and write RTF documents.</span></span> <span data-ttu-id="7b05c-105">En .NET Framework, puede usar el control <xref:System.Windows.Forms.RichTextBox> para crear un procesador de textos que admite RTF y permite que un usuario aplique formato en texto de una manera WYSIWIG.</span><span class="sxs-lookup"><span data-stu-id="7b05c-105">In the .NET Framework, you can use the <xref:System.Windows.Forms.RichTextBox> control to create a word processor that supports RTF and enables a user to apply formatting to text in a WYSIWIG manner.</span></span>  
  
 <span data-ttu-id="7b05c-106">También puede usar el control <xref:System.Windows.Forms.RichTextBox> para quitar mediante programación los códigos de formato RTF de un documento y convertirlo en un texto sin formato.</span><span class="sxs-lookup"><span data-stu-id="7b05c-106">You can also use the <xref:System.Windows.Forms.RichTextBox> control to programmatically remove the RTF formatting codes from a document and convert it to plain text.</span></span> <span data-ttu-id="7b05c-107">No necesita insertar el control en un Windows Form para realizar este tipo de operación.</span><span class="sxs-lookup"><span data-stu-id="7b05c-107">You do not need to embed the control in a Windows Form to perform this kind of operation.</span></span>  
  
### <a name="to-use-the-richtextbox-control-in-a-project"></a><span data-ttu-id="7b05c-108">Para usar el control RichTextBox en un proyecto</span><span class="sxs-lookup"><span data-stu-id="7b05c-108">To use the RichTextBox control in a project</span></span>  
  
1.  <span data-ttu-id="7b05c-109">Agregue una referencia a System.Windows.Forms.dll.</span><span class="sxs-lookup"><span data-stu-id="7b05c-109">Add a reference to System.Windows.Forms.dll.</span></span>  
  
2.  <span data-ttu-id="7b05c-110">Agregue una directiva Using para el espacio de nombres `System.Windows.Forms` (opcional).</span><span class="sxs-lookup"><span data-stu-id="7b05c-110">Add a using directive for the `System.Windows.Forms` namespace (optional).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7b05c-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7b05c-111">Example</span></span>  
 <span data-ttu-id="7b05c-112">En el ejemplo siguiente se convierte un archivo RTF de ejemplo en texto sin formato.</span><span class="sxs-lookup"><span data-stu-id="7b05c-112">The following example converts a sample RTF file to plain text.</span></span> <span data-ttu-id="7b05c-113">El archivo contiene formato RTF (como información de fuentes), cuatro caracteres Unicode y cuatro caracteres ASCII extendidos.</span><span class="sxs-lookup"><span data-stu-id="7b05c-113">The file contains RTF formatting (such as font information), four Unicode characters, and four extended ASCII characters.</span></span> <span data-ttu-id="7b05c-114">El código de ejemplo abre el archivo, pasa su contenido a un <xref:System.Windows.Forms.RichTextBox> como RTF, recupera el contenido como texto, muestra el texto en un <xref:System.Windows.Forms.MessageBox> y genera el texto en un archivo en formato UTF-8.</span><span class="sxs-lookup"><span data-stu-id="7b05c-114">The example code opens the file, passes its content to a <xref:System.Windows.Forms.RichTextBox> as RTF, retrieves the content as text, displays the text in a <xref:System.Windows.Forms.MessageBox>, and outputs the text to a file in UTF-8 format.</span></span>  
  
 <span data-ttu-id="7b05c-115">`MessageBox` y el archivo de salida contienen el texto siguiente:</span><span class="sxs-lookup"><span data-stu-id="7b05c-115">The `MessageBox` and the output file contain the following text:</span></span>  
  
```  
The Greek word for "psyche" is spelled ψυχή. The Greek letters are encoded in Unicode.  
These characters are from the extended ASCII character set (Windows code page 1252):  âäӑå  
```  
  
 <span data-ttu-id="7b05c-116">[!code-cs[csProgGuideStrings#33](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-convert-rtf-to-plain-text_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="7b05c-116">[!code-cs[csProgGuideStrings#33](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-convert-rtf-to-plain-text_1.cs)]</span></span>  
  
 <span data-ttu-id="7b05c-117">Los caracteres RTF se codifican en ocho bits.</span><span class="sxs-lookup"><span data-stu-id="7b05c-117">RTF characters are encoded in eight bits.</span></span> <span data-ttu-id="7b05c-118">En cambio, los usuarios pueden especificar caracteres Unicode además de caracteres ASCII extendidos de páginas de código especificadas.</span><span class="sxs-lookup"><span data-stu-id="7b05c-118">However, users can specify Unicode characters in addition to extended ASCII characters from specified code pages.</span></span> <span data-ttu-id="7b05c-119">Como la propiedad <xref:System.Windows.Forms.RichTextBox.Text%2A?displayProperty=fullName> es de tipo [string](../../../csharp/language-reference/keywords/string.md), los caracteres se codifican como Unicode UTF-16.</span><span class="sxs-lookup"><span data-stu-id="7b05c-119">Because the <xref:System.Windows.Forms.RichTextBox.Text%2A?displayProperty=fullName> property is of type [string](../../../csharp/language-reference/keywords/string.md), the characters are encoded as Unicode UTF-16.</span></span> <span data-ttu-id="7b05c-120">Cualquier carácter ASCII extendido y carácter Unicode del documento RTF de origen se codifica correctamente en la salida de texto.</span><span class="sxs-lookup"><span data-stu-id="7b05c-120">Any extended ASCII characters and Unicode characters from the source RTF document are correctly encoded in the text output.</span></span>  
  
 <span data-ttu-id="7b05c-121">Si usa el método <xref:System.IO.File.WriteAllText%2A?displayProperty=fullName> para escribir el texto en disco, el texto se codificará como UTF-8 (sin una marca de orden de bytes).</span><span class="sxs-lookup"><span data-stu-id="7b05c-121">If you use the <xref:System.IO.File.WriteAllText%2A?displayProperty=fullName> method to write the text to disk, the text will be encoded as UTF-8 (without a Byte Order Mark).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b05c-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="7b05c-122">See Also</span></span>  
 <span data-ttu-id="7b05c-123"><xref:System.Windows.Forms.RichTextBox?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="7b05c-123"><xref:System.Windows.Forms.RichTextBox?displayProperty=fullName></span></span>   
 [<span data-ttu-id="7b05c-124">Cadenas</span><span class="sxs-lookup"><span data-stu-id="7b05c-124">Strings</span></span>](../../../csharp/programming-guide/strings/index.md)

