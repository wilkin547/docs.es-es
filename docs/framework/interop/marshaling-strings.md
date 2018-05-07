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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 52a78e0c3969e879bf2fd1b1f5c41b2caac2ba11
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="marshaling-strings"></a>Serialización de cadenas
La invocación de plataforma copia los parámetros de cadena y los convierte del formato de .NET Framework (Unicode) al formato no administrado (ANSI), si es necesario. Dado que las cadenas administradas son inmutables, la invocación de plataforma no las vuelve a copiar desde la memoria no administrada a la memoria administrada cuando finaliza la función.  
  
 En la tabla siguiente se enumeran las opciones de serialización para cadenas, se describe su uso y se proporciona un vínculo al ejemplo de .NET Framework correspondiente.  
  
|String|Descripción|Ejemplo|  
|------------|-----------------|------------|  
|Por valor.|Pasa las cadenas como parámetros In.|[MsgBox](msgbox-sample.md)|  
|Como resultado.|Devuelve las cadenas desde código no administrado.|[Cadenas](https://msdn.microsoft.com/library/be9e82a3-dc95-4aaa-9396-61b66e467e02(v=vs.100))|  
|Por referencia.|Pasa estructuras como parámetros In/Out mediante <xref:System.Text.StringBuilder>.|[Búferes](https://msdn.microsoft.com/library/e30d36e8-d7c4-4936-916a-8fdbe4d9ffd5(v=vs.100))|  
|En una estructura por valor.|Pasa las cadenas en una estructura que es un parámetro In.|[Structs](https://msdn.microsoft.com/library/96a62265-dcf9-4608-bc0a-1f762ab9f48e(v=vs.100))|  
|En una estructura por referencia **(char\*)**.|Pasa las cadenas en una estructura que es un parámetro In/Out. La función no administrada espera un puntero a un búfer de caracteres y el tamaño del búfer es un miembro de la estructura.|[Cadenas](https://msdn.microsoft.com/library/be9e82a3-dc95-4aaa-9396-61b66e467e02(v=vs.100))|  
|En una estructura por referencia **(char[])**.|Pasa las cadenas en una estructura que es un parámetro In/Out. La función no administrada espera un búfer de caracteres insertado.|[OSInfo](https://msdn.microsoft.com/library/69d89067-507b-41fe-859d-30bf3ff29455(v=vs.100))|  
|En una clase por valor **(char\*)**.|Pasa las cadenas en una clase (una clase es un parámetro In/Out). La función no administrada espera un puntero a un búfer de caracteres.|[OpenFileDlg](https://msdn.microsoft.com/library/b7dea792-cb92-4baf-ac7b-6a24803e6c75(v=vs.100))|  
|En una clase por valor **(char[])**.|Pasa las cadenas en una clase (una clase es un parámetro In/Out). La función no administrada espera un búfer de caracteres insertado.|[OSInfo](https://msdn.microsoft.com/library/69d89067-507b-41fe-859d-30bf3ff29455(v=vs.100))|  
|Como una matriz de cadenas por valor.|Crea una matriz de cadenas que se pasa por valor.|[Matrices](marshaling-different-types-of-arrays.md)|  
|Como una matriz de estructuras que contienen cadenas por valor.|Crea una matriz de estructuras que contienen cadenas y la matriz se pasa por valor.|[Matrices](marshaling-different-types-of-arrays.md)|  
  
## <a name="see-also"></a>Vea también  
 [Serialización de datos con invocación de plataforma](marshaling-data-with-platform-invoke.md)  
 [Tipos de datos de invocación de plataforma](https://msdn.microsoft.com/library/16014d9f-d6bd-481e-83f0-df11377c550f(v=vs.100))  
 [Serialización de clases, estructuras y uniones](marshaling-classes-structures-and-unions.md)  
 [Serialización de matrices de tipos](https://msdn.microsoft.com/library/049b1c1b-228f-4445-88ec-91bc7fd4b1e8(v=vs.100))  
 [Diversos ejemplos de serialización](https://msdn.microsoft.com/library/a915c948-54e9-4d0f-a525-95a77fd8ed70(v=vs.100))
