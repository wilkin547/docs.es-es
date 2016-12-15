---
title: "C&#243;mo: Escribir en un archivo de texto (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "TextWriter.WriteLine"
  - "StreamWriter.Close"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "archivos [C#], archivos de texto"
  - "texto, escribir en archivos [C#]"
ms.assetid: 2e99f184-d88b-4719-a7f1-d9ec482aa809
caps.latest.revision: 23
caps.handback.revision: 23
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# C&#243;mo: Escribir en un archivo de texto (Gu&#237;a de programaci&#243;n de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

En estos ejemplos se muestran varias formas de escribir texto en un archivo.  Los dos primeros ejemplos usan métodos estáticos convenientes en la clase <xref:System.IO.File?displayProperty=fullName> para escribir cada elemento de cualquier IEnumerable\<string\> y una cadena en un archivo de texto.  En el ejemplo 3 se muestra cómo agregar texto a un archivo cuando es necesario procesar cada línea individualmente a medida que se escribe en el archivo.  Los ejemplos 1\-3 sobrescriben todo el contenido del archivo, pero el ejemplo 4 muestra cómo anexar texto a un archivo existente.  
  
 En todos estos ejemplos se escriben literales de cadena en los archivos, pero es más conveniente utilizar el método <xref:System.String.Format%2A>, que tiene muchos controles para escribir diferentes tipos de valores alineados a la derecha o a la izquierda en un campo, con o sin relleno, etc.  También puede usar la característica de [interpolación de cadenas](../../../csharp/language-reference/keywords/interpolated-strings.md) de C\#.  
  
## Ejemplo  
 [!code-cs[csFilesandFolders#3](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-write-to-a-text-file_1.cs)]  
  
 En todos estos ejemplos se escriben literales de cadena en los archivos, pero es más conveniente utilizar el método <xref:System.String.Format%2A>, que tiene muchos controles para escribir diferentes tipos de valores alineados a la derecha o a la izquierda en un campo, con o sin relleno, etc.  También puede usar la característica de [interpolación de cadenas](../../../csharp/language-reference/keywords/interpolated-strings.md) de C\#.  
  
## Programación eficaz  
 Las condiciones siguientes pueden provocar una excepción:  
  
-   El archivo ya existe y es de solo lectura.  
  
-   Puede que el nombre de ruta de acceso sea demasiado largo.  
  
-   Es posible que el disco esté lleno.  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Registro y sistema de archivos](../../../csharp/programming-guide/file-system/file-system-and-the-registry.md)   
 [Ejemplo: guardar una colección en el almacenamiento de la aplicación](http://code.msdn.microsoft.com/CSWinStoreAppSaveCollection-bed5d6e6)