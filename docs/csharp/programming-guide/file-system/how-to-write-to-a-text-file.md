---
title: 'Cómo: Escribir en un archivo de texto (Guía de programación de C#)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- TextWriter.WriteLine
- StreamWriter.Close
helpviewer_keywords:
- files [C#], text files
- text, writing to files [C#]
ms.assetid: 2e99f184-d88b-4719-a7f1-d9ec482aa809
caps.latest.revision: 23
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: fa6de76e3981e0f05b5b192045043422a8a912aa
ms.sourcegitcommit: 935d5267c44f9bce801468ef95f44572f1417e8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="how-to-write-to-a-text-file-c-programming-guide"></a>Cómo: Escribir en un archivo de texto (Guía de programación de C#)
En estos ejemplos se muestran varias formas de escribir texto en un archivo. Los dos primeros ejemplos usan métodos estáticos convenientes en la clase <xref:System.IO.File?displayProperty=nameWithType> para escribir cada elemento de cualquier `IEnumerable<string>` y una cadena en un archivo de texto. En el ejemplo 3 se muestra cómo agregar texto a un archivo cuando es necesario procesar cada línea individualmente a medida que se escribe en el archivo. Los ejemplos 1-3 sobrescriben todo el contenido del archivo, pero el ejemplo 4 muestra cómo anexar texto a un archivo existente.  
  
 Todos estos ejemplos escriben literales de cadena en los archivos. Si quiere aplicar formato al texto escrito en un archivo, use el método <xref:System.String.Format%2A> o la característica [interpolación de cadenas](../../../csharp/language-reference/tokens/interpolated.md) de C#.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[csFilesandFolders#3](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-write-to-a-text-file_1.cs)]  
  
## <a name="robust-programming"></a>Programación sólida  
 Las condiciones siguientes pueden provocar una excepción:  
  
-   El archivo ya existe y es de solo lectura.  
  
-   Puede que el nombre de ruta de acceso sea demasiado largo.  
  
-   Es posible que el disco esté lleno.  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Registro y sistema de archivos (Guía de programación de C#)](../../../csharp/programming-guide/file-system/index.md)  
 [Ejemplo: guardar una colección en el almacenamiento para la aplicación](http://code.msdn.microsoft.com/CSWinStoreAppSaveCollection-bed5d6e6)
