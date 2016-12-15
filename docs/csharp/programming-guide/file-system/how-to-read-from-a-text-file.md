---
title: "C&#243;mo: Leer de un archivo de texto (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
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
  - "StreamReader.ReadToEnd"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "leer datos, archivos de texto"
  - "leer archivos de texto"
  - "archivos de texto, leer"
  - "archivos de texto, escribir"
ms.assetid: 92246c5b-e819-4eea-9370-1a9460e12de3
caps.latest.revision: 17
caps.handback.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# C&#243;mo: Leer de un archivo de texto (Gu&#237;a de programaci&#243;n de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Este ejemplo lee el contenido de un archivo de texto mediante los métodos estáticos <xref:System.IO.File.ReadAllText%2A> y <xref:System.IO.File.ReadAllLines%2A> de la clase <xref:System.IO.File?displayProperty=fullName> .  
  
 Para obtener un ejemplo en el que se utiliza <xref:System.IO.StreamReader>, vea [Cómo: Leer un archivo de texto línea a línea](../../../csharp/programming-guide/file-system/how-to-read-a-text-file-one-line-at-a-time.md).  
  
> [!NOTE]
>  Los archivos que se utilizan en este ejemplo se crean en el tema [Cómo: Escribir en un archivo texto](../../../csharp/programming-guide/file-system/how-to-write-to-a-text-file.md).  
  
## Ejemplo  
 [!code-cs[csFilesandFolders#4](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-read-from-a-text-file_1.cs)]  
  
## Compilar el código  
 Copie el código y péguelo en una aplicación de consola de C\#.  
  
 Si no está utilizando los archivos de texto [Cómo: Escribir en un archivo texto](../../../csharp/programming-guide/file-system/how-to-write-to-a-text-file.md), reemplace el argumento a `ReadAllText` y a `ReadAllLines` con la ruta de acceso adecuada y nombre de archivo en el equipo.  
  
## Programación eficaz  
 Las condiciones siguientes pueden provocar una excepción:  
  
-   El archivo no existe o no existe en la ubicación especificada.  Compruebe la ruta de acceso y la ortografía del nombre de archivo.  
  
## Seguridad de .NET Framework  
 No confíe en el nombre de un archivo para determinar el contenido del archivo.  Por ejemplo, el archivo `myFile.cs` no sea un archivo de código fuente de C\#.  
  
## Vea también  
 <xref:System.IO?displayProperty=fullName>   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Registro y sistema de archivos](../../../csharp/programming-guide/file-system/file-system-and-the-registry.md)