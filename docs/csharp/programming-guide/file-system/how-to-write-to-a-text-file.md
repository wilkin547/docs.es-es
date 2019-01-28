---
title: 'Procedimiento Escribir en un archivo de texto: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- TextWriter.WriteLine
- StreamWriter.Close
helpviewer_keywords:
- files [C#], text files
- text, writing to files [C#]
ms.assetid: 2e99f184-d88b-4719-a7f1-d9ec482aa809
ms.openlocfilehash: ce0321d91835fbdf6c37f4b7736f0de900e9f838
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54666805"
---
# <a name="how-to-write-to-a-text-file-c-programming-guide"></a>Procedimiento Escribir en un archivo de texto (Guía de programación de C#)
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

- [Guía de programación de C#](../../../csharp/programming-guide/index.md)
- [Registro y sistema de archivos (Guía de programación de C#)](../../../csharp/programming-guide/file-system/index.md)
- [Ejemplo: guardar una colección en el almacenamiento para la aplicación](https://code.msdn.microsoft.com/CSWinStoreAppSaveCollection-bed5d6e6)
