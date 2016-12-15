---
title: "C&#243;mo: Convertir RTF en texto sin formato (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "cadenas [C#], conversión desde RTF"
ms.assetid: 3b386a87-899d-4d98-bc82-a980526ddaac
caps.latest.revision: 21
caps.handback.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# C&#243;mo: Convertir RTF en texto sin formato (Gu&#237;a de programaci&#243;n de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

El formato de texto enriquecido \(RTF\) es un formato de documento desarrollado por Microsoft a finales de los ochenta para habilitar el intercambio de documentos entre sistemas operativos.  Tanto Microsoft Word como Wordpad pueden leer y escribir documentos RTF.  En .NET Framework, puede utilizar el control <xref:System.Windows.Forms.RichTextBox> para crear un procesador de textos que admita RTF y permita a un usuario aplicar formato a un texto en modo WYSIWIG.  
  
 También puede utilizar el control <xref:System.Windows.Forms.RichTextBox> para quitar los códigos de formato RTF de un documento y convertirlo en texto sin formato mediante programación.  No es necesario incrustar el control en un Windows Form para realizar este tipo de operación.  
  
### Para utilizar el control RichTextBox en un proyecto  
  
1.  Agregue una referencia a System.Windows.Forms.dll.  
  
2.  Agregue una directiva using para el espacio de nombres `System.Windows.Forms` \(opcional\).  
  
## Ejemplo  
 El ejemplo siguiente convierte un archivo RTF de ejemplo en texto sin formato.  El archivo contiene formato RTF \(como información de fuentes\), cuatro caracteres Unicode, y cuatro caracteres ASCII extendidos.  El código de ejemplo abre el archivo, pasa su contenido a <xref:System.Windows.Forms.RichTextBox> mientras RTF, recupera el contenido como texto, muestra el texto en <xref:System.Windows.Forms.MessageBox>, y genera el texto en un archivo en formato UTF\-8.  
  
 `MessageBox` y el archivo de salida contienen el texto siguiente:  
  
```  
The Greek word for "psyche" is spelled ψυχή. The Greek letters are encoded in Unicode.  
These characters are from the extended ASCII character set (Windows code page 1252):  âäӑå  
  
```  
  
 [!code-cs[csProgGuideStrings#33](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-convert-rtf-to-plain-text_1.cs)]  
  
 Los caracteres RTF se codifican en ocho bits.  Sin embargo, los usuarios pueden especificar caracteres Unicode además de caracteres ASCII extendidos de las páginas de códigos especificadas.  Dado que la propiedad <xref:System.Windows.Forms.RichTextBox.Text%2A?displayProperty=fullName> es de tipo [string](../../../csharp/language-reference/keywords/string.md), los caracteres se codifican como Unicode UTF\-16.  Los caracteres ASCII extendidos y los caracteres Unicode del documento RTF de origen se codifican correctamente en el resultado de texto.  
  
 Si utiliza el método <xref:System.IO.File.WriteAllText%2A?displayProperty=fullName> para escribir el texto en un disco, el texto se codificará como UTF\-8 \(sin una marca de orden de bytes\).  
  
## Vea también  
 <xref:System.Windows.Forms.RichTextBox?displayProperty=fullName>   
 [Cadenas](../../../csharp/programming-guide/strings/index.md)