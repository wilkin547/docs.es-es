---
title: Serialización de cadenas
ms.date: 03/30/2017
helpviewer_keywords:
- marshaling, samples
- platform invoke, marshaling data
- data marshaling, strings
- data marshaling, samples
- data marshaling, platform invoke
- marshaling. strings
- marshaling, platform invoke
- sample applications [.NET Framework], marshaling strings
ms.assetid: e21b078b-70fb-4905-be26-c097ab2433ff
ms.openlocfilehash: 88b6342038f99bf06fa2986c43f422e63cffd31e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124378"
---
# <a name="marshaling-strings"></a>Serialización de cadenas
La invocación de plataforma copia los parámetros de cadena y los convierte del formato de .NET Framework (Unicode) al formato no administrado (ANSI), si es necesario. Dado que las cadenas administradas son inmutables, la invocación de plataforma no las vuelve a copiar desde la memoria no administrada a la memoria administrada cuando finaliza la función.  
  
 En la tabla siguiente se enumeran las opciones de serialización para cadenas, se describe su uso y se proporciona un vínculo al ejemplo de .NET Framework correspondiente.  
  
|String|Descripción|Ejemplo|  
|------------|-----------------|------------|  
|Por valor.|Pasa las cadenas como parámetros In.|[MsgBox](msgbox-sample.md)|  
|Como resultado.|Devuelve las cadenas desde código no administrado.|[Cadenas](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/e765dyyy(v=vs.100))|  
|Por referencia.|Pasa estructuras como parámetros In/Out mediante <xref:System.Text.StringBuilder>.|[Búferes](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/x3txb6xc(v=vs.100))|  
|En una estructura por valor.|Pasa las cadenas en una estructura que es un parámetro In.|[Structs](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/eadtsekz(v=vs.100))|  
|En una estructura por referencia **(char\*)** .|Pasa las cadenas en una estructura que es un parámetro In/Out. La función no administrada espera un puntero a un búfer de caracteres y el tamaño del búfer es un miembro de la estructura.|[Cadenas](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/e765dyyy(v=vs.100))|  
|En una estructura por referencia **(char[])** .|Pasa las cadenas en una estructura que es un parámetro In/Out. La función no administrada espera un búfer de caracteres insertado.|[OSInfo](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/795sy883(v=vs.100))|  
|En una clase por valor **(char\*)** .|Pasa las cadenas en una clase (una clase es un parámetro In/Out). La función no administrada espera un puntero a un búfer de caracteres.|[OpenFileDlg](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w5tyztk9(v=vs.100))|  
|En una clase por valor **(char[])** .|Pasa las cadenas en una clase (una clase es un parámetro In/Out). La función no administrada espera un búfer de caracteres insertado.|[OSInfo](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/795sy883(v=vs.100))|  
|Como una matriz de cadenas por valor.|Crea una matriz de cadenas que se pasa por valor.|[Matrices](marshaling-different-types-of-arrays.md)|  
|Como una matriz de estructuras que contienen cadenas por valor.|Crea una matriz de estructuras que contienen cadenas y la matriz se pasa por valor.|[Matrices](marshaling-different-types-of-arrays.md)|  
  
## <a name="see-also"></a>Vea también

- [Serialización predeterminada para cadenas](default-marshaling-for-strings.md)
- [Serialización de datos con invocación de plataforma](marshaling-data-with-platform-invoke.md)
- [Serialización de clases, estructuras y uniones](marshaling-classes-structures-and-unions.md)
- [Serialización de tipos diferentes de matrices](marshaling-different-types-of-arrays.md)
- [Diversos ejemplos de serialización](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ss9sb93t(v=vs.100))
