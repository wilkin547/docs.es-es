---
title: '#pragma checksum: Referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- '#pragma checksum'
helpviewer_keywords:
- '#pragma checksum [C#]'
ms.assetid: 3673e4ca-6098-4ec1-890f-8fceb2a794a2
ms.openlocfilehash: 1bbb404e1183daa5e68e512e7439b6ae52abd605
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712486"
---
# <a name="pragma-checksum-c-reference"></a>#pragma checksum (Referencia del programador de C#)
Genera sumas de comprobación de archivos de código fuente para ayudar con la depuración de páginas ASP.NET.  
  
## <a name="syntax"></a>Sintaxis  
  
```csharp
#pragma checksum "filename" "{guid}" "checksum bytes"  
```  
  
## <a name="parameters"></a>Parámetros  
 `"filename"`  
 El nombre del archivo que requiere la supervisión para cambios o actualizaciones.  
  
 `"{guid}"`  
 El identificador único global (GUID) del algoritmo hash.  
  
 `"checksum_bytes"`  
 La cadena de dígitos hexadecimales que representa los bytes de la suma de comprobación. Debe ser un número par de dígitos hexadecimales. Un número impar de dígitos genera una advertencia de tiempo de compilación y la directiva se ignora.  
  
## <a name="remarks"></a>Comentarios  
 El depurador de Visual Studio usa una suma de comprobación para asegurarse de que siempre encuentra el código fuente correcto. El compilador calcula la suma de comprobación para un archivo de origen y, después, emite el resultado en el archivo de base de datos del programa (PDB). Después, el depurador usa el archivo PDB para comparar la suma de comprobación que calcula para el archivo de origen.  
  
 Esta solución no funciona para proyectos de ASP.NET, ya que la suma de comprobación calculada es para el archivo de código fuente generado, no para el archivo .aspx. Para solucionar este problema, `#pragma checksum` proporciona compatibilidad de la suma de comprobación con páginas ASP.NET.  
  
 Cuando se crea un proyecto de ASP.NET en Visual C#, el archivo de código fuente generado contiene una suma de comprobación del archivo .aspx desde el que se genera el código fuente. Después, el compilador escribe esta información en el archivo PDB.  
  
 Si el compilador no encuentra ninguna directiva `#pragma checksum` en el archivo, calcula la suma de comprobación y escribe el valor en el archivo PDB.  
  
## <a name="example"></a>Ejemplo  
  
```csharp
class TestClass  
{  
    static int Main()  
    {  
        #pragma checksum "file.cs" "{406EA660-64CF-4C82-B6F0-42D48172A799}" "ab007f1d23d9" // New checksum  
    }  
}  
```  
  
## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Directivas de preprocesador de C#](./index.md)
