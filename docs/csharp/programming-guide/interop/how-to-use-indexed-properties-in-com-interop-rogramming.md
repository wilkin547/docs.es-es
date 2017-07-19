---
title: "Cómo: Usar propiedades indexadas en la programación de interoperabilidad COM (Guía de programación de C#) | Microsoft Docs"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- indexed properties [C#]
- Office programming [C#], indexed properties
- properties [C#], indexed
ms.assetid: 756bfc1e-7c28-4d4d-b114-ac9288c73882
caps.latest.revision: 20
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: 7e33ed084c560470a486ebbb25035a59ddc18565
ms.openlocfilehash: ae550ba7d3f2767cf7cc64a14bc177d15f426c36
ms.contentlocale: es-es
ms.lasthandoff: 05/22/2017

---
# <a name="how-to-use-indexed-properties-in-com-interop-programming-c-programming-guide"></a>Cómo: Utilizar propiedades indizadas en la programación de interoperabilidad COM (Guía de programación de C#)
Las *propiedades indexadas* mejoran la manera en que se usan las propiedades COM con parámetros en la programación de C#. Las propiedades indexadas funcionan junto con otras características de Visual C#, como los [argumentos con nombre y opcionales](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md), un nuevo tipo ([dinámico](../../../csharp/language-reference/keywords/dynamic.md)) y la [información de tipo insertada](../../../csharp/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-visual-studio.md), para mejorar la programación en Microsoft Office.  
  
 En versiones anteriores de C#, los métodos son solo accesibles como propiedades si el método `get` no tiene ningún parámetro y el método `set` tiene solo un parámetro de valor. En cambio, no todas las propiedades COM cumplen esas restricciones. Por ejemplo, la propiedad [Range](http://go.microsoft.com/fwlink/?LinkId=166053) de Excel tiene un descriptor de acceso `get` que requiere un parámetro para el nombre del intervalo. Antes, como no había acceso directo a la propiedad `Range`, había que usar el método `get_Range` en su lugar, como se muestra en el siguiente ejemplo.  
  
 [!code-cs[csProgGuideIndexedProperties#1](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_1.cs)]  
  
 Las propiedades indexadas, en cambio, permiten escribir lo siguiente:  
  
 [!code-cs[csProgGuideIndexedProperties#2](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_2.cs)]  
  
> [!NOTE]
>  En el ejemplo anterior, también se usa la característica [argumentos opcionales](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md), que le permite omitir `Type.Missing`.  
  
 De manera similar, para establecer el valor de la propiedad `Value` de un objeto [Range](https://msdn.microsoft.com/library/microsoft.office.interop.excel.range.aspx) de Visual C# 2008 y versiones anteriores, se necesitan dos argumentos. Uno proporciona un argumento para un parámetro opcional que especifica el tipo del valor del intervalo. El otro proporciona el valor de la propiedad `Value`. Estas técnicas se ilustran en los siguientes ejemplos. En ambos ejemplos, se establece el valor de la celda A1 en `Name`.
  
 [!code-cs[csProgGuideIndexedProperties#3](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_3.cs)]  
  
 Las propiedades indexadas, en cambio, le permiten escribir el siguiente código.  
  
 [!code-cs[csProgGuideIndexedProperties#4](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_4.cs)]  
  
 No es posible crear propiedades indizadas propias. La característica solo admite el uso de las propiedades indizadas existentes.  
  
## <a name="example"></a>Ejemplo  
 En el código siguiente se muestra un ejemplo completo. Para obtener más información sobre cómo preparar un proyecto con acceso a la API de Office, vea [Cómo: Tener acceso a objetos de interoperabilidad de Office mediante las características de Visual C# (Guía de programación de C#)](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md).  
  
 [!code-cs[csProgGuideIndexedProperties#5](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_5.cs)]  
  
## <a name="see-also"></a>Vea también  
 [Argumentos opcionales y con nombre](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md)   
 [dynamic](../../../csharp/language-reference/keywords/dynamic.md)   
 [Uso de tipo dinámico](../../../csharp/programming-guide/types/using-type-dynamic.md)   
 [How to: Use Named and Optional Arguments in Office Programming](../../../csharp/programming-guide/classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md)  [Cómo: Usar argumentos opcionales y con nombre en la programación de Office (Guía de programación de C#)]  
 [Cómo: Tener acceso a objetos de interoperabilidad de Office mediante las características de Visual C#](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md)   
 [Tutorial: Programación de Office](../../../csharp/programming-guide/interop/walkthrough-office-programming.md)
