---
title: "Serialización de cadenas"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
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
caps.latest.revision: 9
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 8d8455d4f1b4dbb463176c06d680b2bd0b1ff9d9
ms.contentlocale: es-es
ms.lasthandoff: 08/21/2017

---
# <a name="marshaling-strings"></a>Serialización de cadenas
La invocación de plataforma copia los parámetros de cadena y los convierte del formato de .NET Framework (Unicode) al formato no administrado (ANSI), si es necesario. Dado que las cadenas administradas son inmutables, la invocación de plataforma no las vuelve a copiar desde la memoria no administrada a la memoria administrada cuando finaliza la función.  
  
 En la tabla siguiente se enumeran las opciones de serialización para cadenas, se describe su uso y se proporciona un vínculo al ejemplo de .NET Framework correspondiente.  
  
|String|Descripción|Ejemplo|  
|------------|-----------------|------------|  
|Por valor.|Pasa las cadenas como parámetros In.|[MsgBox](../../../docs/framework/interop/msgbox-sample.md)|  
|Como resultado.|Devuelve las cadenas desde código no administrado.|[Cadenas](http://msdn.microsoft.com/en-us/be9e82a3-dc95-4aaa-9396-61b66e467e02)|  
|Por referencia.|Pasa estructuras como parámetros In/Out mediante <xref:System.Text.StringBuilder>.|[Búferes](http://msdn.microsoft.com/en-us/e30d36e8-d7c4-4936-916a-8fdbe4d9ffd5)|  
|En una estructura por valor.|Pasa las cadenas en una estructura que es un parámetro In.|[Estructuras](http://msdn.microsoft.com/en-us/96a62265-dcf9-4608-bc0a-1f762ab9f48e)|  
|En una estructura por referencia **(char\*)**.|Pasa las cadenas en una estructura que es un parámetro In/Out. La función no administrada espera un puntero a un búfer de caracteres y el tamaño del búfer es un miembro de la estructura.|[Cadenas](http://msdn.microsoft.com/en-us/be9e82a3-dc95-4aaa-9396-61b66e467e02)|  
|En una estructura por referencia **(char[])**.|Pasa las cadenas en una estructura que es un parámetro In/Out. La función no administrada espera un búfer de caracteres insertado.|[OSInfo](http://msdn.microsoft.com/en-us/69d89067-507b-41fe-859d-30bf3ff29455)|  
|En una clase por valor **(char\*)**.|Pasa las cadenas en una clase (una clase es un parámetro In/Out). La función no administrada espera un puntero a un búfer de caracteres.|[OpenFileDlg](http://msdn.microsoft.com/en-us/b7dea792-cb92-4baf-ac7b-6a24803e6c75)|  
|En una clase por valor **(char[])**.|Pasa las cadenas en una clase (una clase es un parámetro In/Out). La función no administrada espera un búfer de caracteres insertado.|[OSInfo](http://msdn.microsoft.com/en-us/69d89067-507b-41fe-859d-30bf3ff29455)|  
|Como una matriz de cadenas por valor.|Crea una matriz de cadenas que se pasa por valor.|[Matrices](../../../docs/framework/interop/marshaling-different-types-of-arrays.md)|  
|Como una matriz de estructuras que contienen cadenas por valor.|Crea una matriz de estructuras que contienen cadenas y la matriz se pasa por valor.|[Matrices](../../../docs/framework/interop/marshaling-different-types-of-arrays.md)|  
  
## <a name="see-also"></a>Vea también  
 [Serialización de datos con invocación de plataforma](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md)   
 [Tipos de datos de invocación de plataforma](http://msdn.microsoft.com/en-us/16014d9f-d6bd-481e-83f0-df11377c550f)   
 [Serialización de clases, estructuras y uniones](../../../docs/framework/interop/marshaling-classes-structures-and-unions.md)   
 [Calcular las referencias de matrices de tipos](http://msdn.microsoft.com/en-us/049b1c1b-228f-4445-88ec-91bc7fd4b1e8)   
 [Diversos ejemplos de serialización](http://msdn.microsoft.com/en-us/a915c948-54e9-4d0f-a525-95a77fd8ed70)

