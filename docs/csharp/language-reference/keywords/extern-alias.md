---
description: 'alias externo: Referencia de C#'
title: 'alias externo: Referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- alias_CSharpKeyword
helpviewer_keywords:
- extern alias keyword [C#]
- aliases [C#], extern keyword
- aliases, extern keyword
ms.assetid: f487bf4f-c943-4fca-851b-e540c83d9027
ms.openlocfilehash: 5ecafa5a989bc183d7f52ac3d4b4d50a81b36014
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203350"
---
# <a name="extern-alias-c-reference"></a>alias externo (Referencia de C#)

Es posible que deba hacer referencia a dos versiones de ensamblados que tienen los mismos nombres de tipo completos. Por ejemplo, es posible que tenga que usar dos o más versiones de un ensamblado en la misma aplicación. Mediante el uso de un alias de ensamblado externo, los espacios de nombres de cada ensamblado pueden ajustarse en espacios de nombres de nivel de raíz denominados por el alias, lo que permite que se usen en el mismo archivo.  
  
> [!NOTE]
> La palabra clave [extern](./extern.md) también se usa como un modificador de método, y declara un método escrito en código no administrado.  
  
 Para hacer referencia a dos ensamblados con los mismos nombres de tipo completos, debe especificarse un alias en un símbolo del sistema, como sigue:  
  
 `/r:GridV1=grid.dll`  
  
 `/r:GridV2=grid20.dll`  
  
 Esto crea los alias externos `GridV1` y `GridV2`. Para usar estos alias desde dentro de un programa, se hace referencia a ellos mediante la palabra clave `extern`. Por ejemplo:  
  
 `extern alias GridV1;`  
  
 `extern alias GridV2;`  
  
 Cada declaración de alias externo introduce un espacio de nombres de nivel de raíz adicional que es semejante al espacio de nombres global (pero que no se encuentra en su interior). Por tanto, se puede hacer referencia a los tipos de cada ensamblado sin ambigüedad mediante su nombre completo, con raíz en el alias de espacio de nombres adecuado.  
  
 En el ejemplo anterior, `GridV1::Grid` sería el control de cuadrícula de `grid.dll`, y `GridV2::Grid` sería el control de cuadrícula de `grid20.dll`.  
  
## <a name="using-visual-studio"></a>Uso de Visual Studio

Si usa Visual Studio, los alias se pueden proporcionar de manera similar.

Agregue una referencia de *grid.dll* y *grid20.dll* al proyecto en Visual Studio. Abra una pestaña de propiedades y cambie los alias de global a GridV1 y GridV2, respectivamente.

Use estos alias igual que antes.

```csharp
 extern alias GridV1;  
  
 extern alias GridV2;  
```

Ahora puede crear un alias para un espacio de nombres o un tipo *mediante la directiva de alias*. Para más información, consulte la [directiva using](using-directive.md).

```csharp
using Class1V1 = GridV1::Namespace.Class1;

using Class1V2 = GridV2::Namespace.Class1;
```

## <a name="c-language-specification"></a>Especificación del lenguaje C#  

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Palabras clave de C#](./index.md)
- [:: !](../operators/namespace-alias-qualifier.md)
- [-reference (Opciones del compilador de C#)](../compiler-options/reference-compiler-option.md)
