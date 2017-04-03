---
title: "Cómo: Escribir en un archivo de texto (Guía de programación de C#) | Microsoft Docs"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- TextWriter.WriteLine
- StreamWriter.Close
dev_langs:
- CSharp
helpviewer_keywords:
- files [C#], text files
- text, writing to files [C#]
ms.assetid: 2e99f184-d88b-4719-a7f1-d9ec482aa809
caps.latest.revision: 23
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: c56095582561e4df19b164bc9a46b69a14da7c9d
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-write-to-a-text-file-c-programming-guide"></a>Cómo: Escribir en un archivo de texto (Guía de programación de C#)
En estos ejemplos se muestran varias formas de escribir texto en un archivo.  En los dos primeros ejemplos se usan métodos estáticos convenientes en la clase <xref:System.IO.File?displayProperty=fullName> para escribir cada elemento de cualquier IEnumerable\<string> y una cadena en un archivo de texto.  En el ejemplo 3 se muestra cómo agregar texto a un archivo cuando es necesario procesar cada línea individualmente a medida que se escribe en el archivo.  Los ejemplos 1-3 sobrescriben todo el contenido del archivo, pero el ejemplo 4 muestra cómo anexar texto a un archivo existente.  
  
 En todos estos ejemplos se escriben literales de cadena en los archivos, pero es más conveniente usar el método <xref:System.String.Format%2A>, que tiene muchos controles para escribir diferentes tipos de valores alineados a la derecha o a la izquierda en un campo, con o sin relleno, etc.  También puede usar la característica de [interpolación de cadenas](../../../csharp/language-reference/keywords/interpolated-strings.md) de C#.  
  
## <a name="example"></a>Ejemplo  
 [!code-cs[csFilesandFolders#3](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-write-to-a-text-file_1.cs)]  
  
 En todos estos ejemplos se escriben literales de cadena en los archivos, pero es más conveniente usar el método <xref:System.String.Format%2A>, que tiene muchos controles para escribir diferentes tipos de valores alineados a la derecha o a la izquierda en un campo, con o sin relleno, etc.  También puede usar la característica de [interpolación de cadenas](../../../csharp/language-reference/keywords/interpolated-strings.md) de C#.  
  
## <a name="robust-programming"></a>Programación sólida  
 Las condiciones siguientes pueden provocar una excepción:  
  
-   El archivo ya existe y es de solo lectura.  
  
-   Puede que el nombre de ruta de acceso sea demasiado largo.  
  
-   Es posible que el disco esté lleno.  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Registro y sistema de archivos (Guía de programación de C#)](../../../csharp/programming-guide/file-system/index.md)   
 [Ejemplo: guardar una colección en el almacenamiento para la aplicación](http://code.msdn.microsoft.com/CSWinStoreAppSaveCollection-bed5d6e6)
