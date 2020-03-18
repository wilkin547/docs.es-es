---
title: 'Procedimiento Escribir en un archivo de texto: Guía de programación de C#'
ms.date: 07/20/2015
f1_keywords:
- TextWriter.WriteLine
- StreamWriter.Close
helpviewer_keywords:
- files [C#], text files
- text, writing to files [C#]
ms.assetid: 2e99f184-d88b-4719-a7f1-d9ec482aa809
ms.openlocfilehash: ac16fb971eae5654a55e2f1753d78a6458f03315
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "75712252"
---
# <a name="how-to-write-to-a-text-file-c-programming-guide"></a>Procedimiento Escribir en un archivo de texto (Guía de programación de C#)
En estos ejemplos se muestran varias formas de escribir texto en un archivo. Los dos primeros ejemplos usan métodos estáticos convenientes en la clase <xref:System.IO.File?displayProperty=nameWithType> para escribir cada elemento de cualquier `IEnumerable<string>` y una cadena en un archivo de texto. En el ejemplo 3 se muestra cómo agregar texto a un archivo cuando es necesario procesar cada línea individualmente a medida que se escribe en el archivo. Los ejemplos 1-3 sobrescriben todo el contenido del archivo, pero el ejemplo 4 muestra cómo anexar texto a un archivo existente.  
  
 Todos estos ejemplos escriben literales de cadena en los archivos. Si quiere aplicar formato al texto escrito en un archivo, use el método <xref:System.String.Format%2A> o la característica [interpolación de cadenas](../../language-reference/tokens/interpolated.md) de C#.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[csFilesandFolders#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#3)]  
  
## <a name="robust-programming"></a>Programación sólida  
 Las condiciones siguientes pueden provocar una excepción:  
  
- El archivo ya existe y es de solo lectura.  
  
- Puede que el nombre de ruta de acceso sea demasiado largo.  
  
- Es posible que el disco esté lleno.  
  
## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Registro y sistema de archivos (Guía de programación de C#)](./index.md)
- [Ejemplo: guardar una colección en el almacenamiento para la aplicación](https://code.msdn.microsoft.com/CSWinStoreAppSaveCollection-bed5d6e6)
