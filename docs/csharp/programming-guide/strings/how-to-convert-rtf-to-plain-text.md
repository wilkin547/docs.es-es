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
# <a name="how-to-convert-rtf-to-plain-text-c-programming-guide"></a>Cómo: Convertir RTF en texto sin formato (Guía de programación de C#)
Formato de texto enriquecido (RTF) es un formato de documento desarrollado por Microsoft a finales de los años 80 para permitir el intercambio de documentos en sistemas operativos. Microsoft Word y WordPad pueden leer y escribir documentos RTF. En .NET Framework, puede usar el control <xref:System.Windows.Forms.RichTextBox> para crear un procesador de textos que admite RTF y permite que un usuario aplique formato en texto de una manera WYSIWIG.  
  
 También puede usar el control <xref:System.Windows.Forms.RichTextBox> para quitar mediante programación los códigos de formato RTF de un documento y convertirlo en un texto sin formato. No necesita insertar el control en un Windows Form para realizar este tipo de operación.  
  
### <a name="to-use-the-richtextbox-control-in-a-project"></a>Para usar el control RichTextBox en un proyecto  
  
1.  Agregue una referencia a System.Windows.Forms.dll.  
  
2.  Agregue una directiva Using para el espacio de nombres `System.Windows.Forms` (opcional).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se convierte un archivo RTF de ejemplo en texto sin formato. El archivo contiene formato RTF (como información de fuentes), cuatro caracteres Unicode y cuatro caracteres ASCII extendidos. El código de ejemplo abre el archivo, pasa su contenido a un <xref:System.Windows.Forms.RichTextBox> como RTF, recupera el contenido como texto, muestra el texto en un <xref:System.Windows.Forms.MessageBox> y genera el texto en un archivo en formato UTF-8.  
  
 `MessageBox` y el archivo de salida contienen el texto siguiente:  
  
```  
The Greek word for "psyche" is spelled ψυχή. The Greek letters are encoded in Unicode.  
These characters are from the extended ASCII character set (Windows code page 1252):  âäӑå  
```  
  
 [!code-cs[csProgGuideStrings#33](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-convert-rtf-to-plain-text_1.cs)]  
  
 Los caracteres RTF se codifican en ocho bits. En cambio, los usuarios pueden especificar caracteres Unicode además de caracteres ASCII extendidos de páginas de código especificadas. Como la propiedad <xref:System.Windows.Forms.RichTextBox.Text%2A?displayProperty=fullName> es de tipo [string](../../../csharp/language-reference/keywords/string.md), los caracteres se codifican como Unicode UTF-16. Cualquier carácter ASCII extendido y carácter Unicode del documento RTF de origen se codifica correctamente en la salida de texto.  
  
 Si usa el método <xref:System.IO.File.WriteAllText%2A?displayProperty=fullName> para escribir el texto en disco, el texto se codificará como UTF-8 (sin una marca de orden de bytes).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.RichTextBox?displayProperty=fullName>   
 [Cadenas](../../../csharp/programming-guide/strings/index.md)

