---
title: Restricción de la accesibilidad del descriptor de acceso - Guía de programación de C#
ms.date: 07/20/2015
helpviewer_keywords:
- read-only properties [C#]
- read-only indexers [C#]
- accessors [C#]
- properties [C#], read-only
- asymmetric accessor accessibility [C#]
- indexers [C#], read-only
ms.assetid: 6e655798-e112-4301-a680-6310a6e012e1
ms.openlocfilehash: a332fef814f0c81914eb7b8c308de68f719fbaac
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "75714691"
---
# <a name="restricting-accessor-accessibility-c-programming-guide"></a>Restringir la accesibilidad del descriptor de acceso (Guía de programación de C#)
Las partes [get](../../language-reference/keywords/get.md) y [set](../../language-reference/keywords/set.md) de una propiedad o un indexador se denominan *descriptores de acceso*. De forma predeterminada, estos descriptores de acceso tienen la misma visibilidad o nivel de acceso de la propiedad o el indexador al que pertenecen. Para obtener más información, vea [Niveles de accesibilidad](../../language-reference/keywords/accessibility-levels.md). En cambio, a veces resulta útil restringir el acceso a uno de estos descriptores de acceso. Normalmente, esto implica restringir la accesibilidad del descriptor de acceso `set`, mientras que se mantiene el descriptor de acceso `get` accesible públicamente. Por ejemplo:  
  
 [!code-csharp[csProgGuideIndexers#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideIndexers/CS/Indexers.cs#6)]  
  
 En este ejemplo, una propiedad denominada `Name` define un descriptor de acceso `get` y `set`. El descriptor de acceso `get` recibe el nivel de accesibilidad de la propiedad, `public` en este caso, mientras que el descriptor de acceso `set` se restringe explícitamente al aplicar el modificador de acceso [protected](../../language-reference/keywords/protected.md) al propio descriptor de acceso.  
  
## <a name="restrictions-on-access-modifiers-on-accessors"></a>Restricciones en los modificadores de acceso en descriptores de acceso  
 Usar los modificadores de descriptor de acceso en propiedades o indexadores está sujeto a estas condiciones:  
  
- No puede usar los modificadores de descriptor de acceso en una interfaz o en una implementación explícita del miembro [interface](../../language-reference/keywords/interface.md).  
  
- Puede usar modificadores de descriptor de acceso solo si la propiedad o el indexador tienen los descriptores de acceso `set` y `get`. En este caso, se permite el modificador solo en uno de los dos descriptores de acceso.  
  
- Si la propiedad o el indexador tienen un modificador [override](../../language-reference/keywords/override.md), el modificador de descriptor de acceso debe coincidir con el descriptor de acceso del descriptor de acceso invalidado, si lo hay.  
  
- El nivel de accesibilidad del descriptor de acceso debe ser más restrictivo que el nivel de accesibilidad de la propiedad o el indexador.  
  
## <a name="access-modifiers-on-overriding-accessors"></a>Modificadores de acceso en descriptores de acceso de invalidación  
 Al invalidar una propiedad o un indexador, los descriptores de acceso invalidados deben ser accesibles para el código de invalidación. Además, la accesibilidad de la propiedad y el indexador y sus descriptores de acceso debe coincidir con la propiedad y el indexador invalidados correspondientes y sus descriptores de acceso. Por ejemplo:  
  
 [!code-csharp[csProgGuideIndexers#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideIndexers/CS/Indexers.cs#7)]  
  
## <a name="implementing-interfaces"></a>Implementar interfaces  
 Al usar un descriptor de acceso para implementar una interfaz, este no puede tener un modificador de acceso. En cambio, si implementa la interfaz con un descriptor de acceso, como `get`, el otro descriptor de acceso puede tener un modificador de acceso, como en el ejemplo siguiente:  
  
 [!code-csharp[csProgGuideIndexers#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideIndexers/CS/Indexers.cs#8)]  
  
## <a name="accessor-accessibility-domain"></a>Dominio de accesibilidad de descriptor de acceso  
 Si usa un modificador de acceso en el descriptor de acceso, el [dominio de accesibilidad](../../language-reference/keywords/accessibility-domain.md) del descriptor de acceso viene determinado por este modificador.  
  
 Si no ha usado un modificador de acceso en el descriptor de acceso, el dominio de accesibilidad del descriptor de acceso viene determinado por el nivel de accesibilidad de la propiedad o el indexador.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, se incluyen tres clases: `BaseClass`, `DerivedClass` y `MainClass`. Hay dos propiedades en `BaseClass`, `Name` y `Id` en ambas clases. En el ejemplo, se muestra cómo la propiedad `Id` en `DerivedClass` se puede ocultar con la propiedad `Id` en `BaseClass` al usar un modificador de acceso restrictivo como [protected](../../language-reference/keywords/protected.md) o [private](../../language-reference/keywords/private.md). Por tanto, cuando asigna valores a esta propiedad, se llama en su lugar a la propiedad en la clase `BaseClass`. Si se reemplaza el modificador de acceso por [public](../../language-reference/keywords/public.md), la propiedad será accesible.  
  
 En el ejemplo, también se muestra que un modificador de acceso restrictivo, como `private` o `protected`, en el descriptor de acceso `set` de la propiedad `Name` en `DerivedClass` impide el acceso al descriptor de acceso y genera un error al asignárselo.  
  
 [!code-csharp[csProgGuideIndexers#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideIndexers/CS/Indexers.cs#5)]  
  
## <a name="comments"></a>Comentarios  
 Tenga en cuenta que, si reemplaza la declaración `new private string Id` por `new public string Id`, obtendrá el resultado:  
  
 `Name and ID in the base class: Name-BaseClass, ID-BaseClass`  
  
 `Name and ID in the derived class: John, John123`  
  
## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Propiedades](./properties.md)
- [Indizadores](../indexers/index.md)
- [Modificadores de acceso](./access-modifiers.md)
