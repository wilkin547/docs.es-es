---
title: 'Procedimiento Utilizar propiedades indizadas en la programación de interoperabilidad COM: Guía de programación de C#'
ms.date: 07/20/2015
helpviewer_keywords:
- indexed properties [C#]
- Office programming [C#], indexed properties
- properties [C#], indexed
ms.assetid: 756bfc1e-7c28-4d4d-b114-ac9288c73882
ms.openlocfilehash: 864e2274f0e0e79b4843e0bb67b5c4384eac8588
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712070"
---
# <a name="how-to-use-indexed-properties-in-com-interop-programming-c-programming-guide"></a>Procedimiento Utilizar propiedades indizadas en la programación de interoperabilidad COM (Guía de programación de C#)
Las *propiedades indexadas* mejoran la manera en que se usan las propiedades COM con parámetros en la programación de C#. Las propiedades indexadas funcionan junto con otras características de Visual C#, como los [argumentos con nombre y opcionales](../classes-and-structs/named-and-optional-arguments.md), un nuevo tipo ([dinámico](../../language-reference/builtin-types/reference-types.md)) y la [información de tipo insertada](../../../standard/assembly/embed-types-visual-studio.md), para mejorar la programación en Microsoft Office.  
  
 En versiones anteriores de C#, los métodos son solo accesibles como propiedades si el método `get` no tiene ningún parámetro y el método `set` tiene solo un parámetro de valor. En cambio, no todas las propiedades COM cumplen esas restricciones. Por ejemplo, la propiedad <xref:Microsoft.Office.Interop.Excel.Range.Range%2A> de Excel tiene un descriptor de acceso `get` que requiere un parámetro para el nombre del intervalo. Antes, como no había acceso directo a la propiedad `Range`, había que usar el método `get_Range` en su lugar, como se muestra en el siguiente ejemplo.  
  
 [!code-csharp[csProgGuideIndexedProperties#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#1)]  
  
 Las propiedades indexadas, en cambio, permiten escribir lo siguiente:  
  
 [!code-csharp[csProgGuideIndexedProperties#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#2)]  
  
> [!NOTE]
> En el ejemplo anterior, también se usa la característica [argumentos opcionales](../classes-and-structs/named-and-optional-arguments.md), que le permite omitir `Type.Missing`.  
  
 De manera similar, para establecer el valor de la propiedad `Value` de un objeto <xref:Microsoft.Office.Interop.Excel.Range> en C# 3.0 y versiones anteriores, se necesitan dos argumentos. Uno proporciona un argumento para un parámetro opcional que especifica el tipo del valor del intervalo. El otro proporciona el valor de la propiedad `Value`. Estas técnicas se ilustran en los siguientes ejemplos. En ambos ejemplos, se establece el valor de la celda A1 en `Name`.
  
 [!code-csharp[csProgGuideIndexedProperties#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#3)]  
  
 Las propiedades indexadas, en cambio, le permiten escribir el siguiente código.  
  
 [!code-csharp[csProgGuideIndexedProperties#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#4)]  
  
 No es posible crear propiedades indizadas propias. La característica solo admite el uso de las propiedades indizadas existentes.  
  
## <a name="example"></a>Ejemplo  
 En el código siguiente se muestra un ejemplo completo. Para más información sobre cómo preparar un proyecto con acceso a la API de Office, consulte [Procedimiento Tener acceso a objetos de interoperabilidad de Office mediante las características de Visual C# (Guía de programación de C#)](./how-to-access-office-onterop-objects.md).
  
 [!code-csharp[csProgGuideIndexedProperties#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#5)]  
  
## <a name="see-also"></a>Vea también

- [Argumentos opcionales y con nombre](../classes-and-structs/named-and-optional-arguments.md)
- [dynamic](../../language-reference/builtin-types/reference-types.md)
- [Uso de tipo dinámico](../types/using-type-dynamic.md)
- [Procedimiento para usar argumentos opcionales y con nombre en la programación de Office](../classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md)
- [Procedimiento para acceder a objetos de interoperabilidad de Office mediante características de C#](./how-to-access-office-onterop-objects.md)
- [Tutorial: Programación de Office](./walkthrough-office-programming.md)
