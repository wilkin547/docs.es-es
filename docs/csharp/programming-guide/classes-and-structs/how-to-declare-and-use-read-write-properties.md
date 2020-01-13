---
title: Procedimiento para declarar y usar propiedades de lectura y escritura - Guía de programación de C#
ms.date: 07/20/2015
helpviewer_keywords:
- get accessor [C#], declaring properties
- set accessor [C#]
- properties [C#], declaring
- read/write properties [C#]
- accessors [C#], declaring properties with
ms.assetid: a4962fef-af7e-4c4b-a929-4ae4d646ab8a
ms.openlocfilehash: 5b880cfc3ace197a3bad2f707cf55543dbe7b78e
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714927"
---
# <a name="how-to-declare-and-use-read-write-properties-c-programming-guide"></a>Procedimiento para declarar y usar propiedades de lectura y escritura (Guía de programación de C#)
Las propiedades proporcionan la comodidad de los miembros de datos públicos sin los riesgos que provienen del acceso sin comprobar, sin controlar y sin proteger a los datos de un objeto. Esto se consigue mediante los *descriptores de acceso*: métodos especiales que asignan y recuperan valores del miembro de datos subyacente. El descriptor de acceso [set](../../language-reference/keywords/set.md) permite que los miembros de datos se asignen, y el descriptor de acceso [get](../../language-reference/keywords/get.md) recupera los valores de los miembros de datos.  
  
 En este ejemplo se muestra una clase `Person` que tiene dos propiedades: `Name` (string) y `Age` (int). Ambas propiedades proporcionan descriptores de acceso `get` y `set`, de manera que se consideran propiedades de lectura y escritura.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[csProgGuideObjects#33](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#33)]  
  
## <a name="robust-programming"></a>Programación sólida  
 En el ejemplo anterior, las propiedades `Name` y `Age` son [públicas](../../language-reference/keywords/public.md) e incluyen un descriptor de acceso `get` y `set`. Esto permite que cualquier objeto lea y escriba estas propiedades. En cambio, a veces esto es conveniente para excluir uno de los descriptores de acceso. Omitir el descriptor de acceso `set`, por ejemplo, hace que la propiedad sea de solo lectura:  
  
 [!code-csharp[csProgGuideObjects#87](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#87)]  
  
 De manera alternativa, puede exponer un descriptor de acceso públicamente pero hacer que el otro sea privado o esté protegido. Para obtener más información, vea [Accesibilidad del descriptor de acceso asimétrico](./restricting-accessor-accessibility.md).  
  
 Una vez que se declaren las propiedades, pueden usarse como si fueran campos de la clase. Esto permite una sintaxis muy natural cuando ambos obtienen y establecen el valor de una propiedad, como se muestra en las instrucciones siguientes:  
  
 [!code-csharp[csProgGuideObjects#35](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#35)]  
  
 Tenga en cuenta que en un método `set` de la propiedad está disponible una variable `value` especial. Esta variable contiene el valor que el usuario ha especificado, por ejemplo:  
  
 [!code-csharp[csProgGuideObjects#36](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#36)]  
  
 Tenga en cuenta la sintaxis pura para incrementar la propiedad `Age` en un objeto `Person`:  
  
 [!code-csharp[csProgGuideObjects#37](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#37)]  
  
 Si los métodos `set` y `get` independientes se han usado para modelar las propiedades, el código equivalente puede tener este aspecto:  
  
```csharp  
person.SetAge(person.GetAge() + 1);   
```  
  
 El método `ToString` se invalida en este ejemplo:  
  
 [!code-csharp[csProgGuideObjects#38](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#38)]  
  
 Tenga en cuenta que `ToString` no se usa explícitamente en el programa. Se invoca de manera predeterminada mediante las llamadas a `WriteLine`.  
  
## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Propiedades](./properties.md)
- [Clases y structs](./index.md)
