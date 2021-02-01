---
title: Procedimiento para declarar y usar propiedades de lectura y escritura - Guía de programación de C#
description: Obtenga información sobre cómo usar propiedades de lectura y escritura en C#. Este ejemplo incluye dos propiedades, cada una con descriptores de acceso get y set, por lo que son de lectura y escritura.
ms.date: 07/20/2015
helpviewer_keywords:
- get accessor [C#], declaring properties
- set accessor [C#]
- properties [C#], declaring
- read/write properties [C#]
- accessors [C#], declaring properties with
ms.topic: how-to
ms.custom: contperf-fy21q2
ms.assetid: a4962fef-af7e-4c4b-a929-4ae4d646ab8a
ms.openlocfilehash: 75f3b4d6fa8595734cf1310c08281c26c829fd84
ms.sourcegitcommit: 8299abfbd5c49b596d61f1e4d09bc6b8ba055b36
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/27/2021
ms.locfileid: "98899027"
---
# <a name="how-to-declare-and-use-read-write-properties-c-programming-guide"></a>Procedimiento para declarar y usar propiedades de lectura y escritura (Guía de programación de C#)

Las propiedades proporcionan la comodidad de los miembros de datos públicos sin los riesgos que provienen del acceso sin comprobar, sin controlar y sin proteger a los datos de un objeto. Esto se consigue mediante los *descriptores de acceso*: métodos especiales que asignan y recuperan valores del miembro de datos subyacente. El descriptor de acceso [set](../../language-reference/keywords/set.md) permite que los miembros de datos se asignen, y el descriptor de acceso [get](../../language-reference/keywords/get.md) recupera los valores de los miembros de datos.  
  
 En este ejemplo se muestra una clase `Person` que tiene dos propiedades: `Name` (string) y `Age` (int). Ambas propiedades proporcionan descriptores de acceso `get` y `set`, de manera que se consideran propiedades de lectura y escritura.  
  
## <a name="example"></a>Ejemplo  

 [!code-csharp[properties#1](snippets/how-to-declare-and-use-read-write-properties/Program.cs#1)]
  
## <a name="robust-programming"></a>Programación sólida  

 En el ejemplo anterior, las propiedades `Name` y `Age` son [públicas](../../language-reference/keywords/public.md) e incluyen un descriptor de acceso `get` y `set`. Esto permite que cualquier objeto lea y escriba estas propiedades. En cambio, a veces esto es conveniente para excluir uno de los descriptores de acceso. Omitir el descriptor de acceso `set`, por ejemplo, hace que la propiedad sea de solo lectura:  
  
 [!code-csharp[properties#2](snippets/how-to-declare-and-use-read-write-properties/Program.cs#2)]
  
 De manera alternativa, puede exponer un descriptor de acceso públicamente pero hacer que el otro sea privado o esté protegido. Para obtener más información, vea [Accesibilidad del descriptor de acceso asimétrico](./restricting-accessor-accessibility.md).  
  
 Una vez que se declaren las propiedades, pueden usarse como si fueran campos de la clase. Esto permite una sintaxis muy natural cuando ambos obtienen y establecen el valor de una propiedad, como se muestra en las instrucciones siguientes:  
  
 [!code-csharp[properties#3](snippets/how-to-declare-and-use-read-write-properties/Program.cs#3)]
  
 Tenga en cuenta que en un método `set` de la propiedad está disponible una variable `value` especial. Esta variable contiene el valor que el usuario ha especificado, por ejemplo:  
  
 [!code-csharp[properties#4](snippets/how-to-declare-and-use-read-write-properties/Program.cs#4)]
  
 Tenga en cuenta la sintaxis pura para incrementar la propiedad `Age` en un objeto `Person`:  
  
 [!code-csharp[properties#5](snippets/how-to-declare-and-use-read-write-properties/Program.cs#5)]
  
 Si los métodos `set` y `get` independientes se han usado para modelar las propiedades, el código equivalente puede tener este aspecto:  
  
```csharp  
person.SetAge(person.GetAge() + 1);
```  
  
 El método `ToString` se invalida en este ejemplo:  
  
 [!code-csharp[properties#6](snippets/how-to-declare-and-use-read-write-properties/Program.cs#6)]
  
 Tenga en cuenta que `ToString` no se usa explícitamente en el programa. Se invoca de manera predeterminada mediante las llamadas a `WriteLine`.  
  
## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Propiedades](./properties.md)
- [Clases y structs](./index.md)
