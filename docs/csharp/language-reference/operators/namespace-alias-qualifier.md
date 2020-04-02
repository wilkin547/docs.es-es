---
title: 'Operador :: (referencia de C#)'
ms.date: 08/09/2019
f1_keywords:
- ::_CSharpKeyword
- global_CSharpKeyword
helpviewer_keywords:
- ':: operator [C#]'
- namespace alias qualifier [C#]
- namespace [C#]
- global keyword [C#]
ms.assetid: 698b5a73-85cf-4e0e-9e8e-6496887f8527
ms.openlocfilehash: 84c418627462f83630fe5072a0b0e2089f6588f6
ms.sourcegitcommit: 2514f4e3655081dcfe1b22470c0c28500f952c42
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "79507131"
---
# <a name="-operator-c-reference"></a>Operador :: (referencia de C#)

Use el calificador de alias de espacio de nombres `::` para acceder a un miembro del espacio de nombres con alias. Solo puede usar el calificador `::` entre dos identificadores. El identificador de la izquierda puede ser cualquiera de los siguientes alias:

- Un alias de espacio de nombres creado con una [directiva de alias using](../keywords/using-directive.md):

  ```csharp
  using forwinforms = System.Drawing;
  using forwpf = System.Windows;
  
  public class Converters
  {
      public static forwpf::Point Convert(forwinforms::Point point) => new forwpf::Point(point.X, point.Y);
  }
  ```

- Un [alias externo](../keywords/extern-alias.md).
- El alias `global`, que es el alias del espacio de nombres global. El espacio de nombres global es el espacio de nombres que contiene los espacios de nombres y los tipos que no se declaran dentro de un espacio de nombres con nombre. Cuando se usa con el calificador `::`, el alias `global` siempre hace referencia al espacio de nombres global, incluso si está el alias del espacio de nombres `global` definido por el usuario.

  En el ejemplo siguiente se usa el alias `global` para tener acceso al espacio de nombres <xref:System> de .NET, que es miembro del espacio de nombres global. Sin el alias `global`, se tendría acceso al espacio de nombres `System` definido por el usuario, que es miembro del espacio de nombres `MyCompany.MyProduct`:

  ```csharp
  namespace MyCompany.MyProduct.System
  {
      class Program
      {
          static void Main() => global::System.Console.WriteLine("Using global alias");
      }

      class Console
      {
          string Suggestion => "Consider renaming this class";
      }
  }
  ```

  > [!NOTE]
  > La palabra clave `global` es el alias de espacio de nombres global solo cuando es el identificador izquierdo del calificador `::`.

También puede usar el token [`.`](member-access-operators.md#member-access-expression-) para acceder a un miembro de un espacio de nombres con alias. Sin embargo, el operador `.` también se usa para acceder a un miembro del tipo. El calificador `::` garantiza que el identificador de la izquierda siempre hace referencia a un alias de espacio de nombres, aunque exista un tipo o un espacio de nombres con el mismo nombre.

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para más información, consulte la sección sobre [calificadores de alias de espacio de nombres](~/_csharplang/spec/namespaces.md#namespace-alias-qualifiers) de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Operadores de C#](index.md)
- [Uso de espacios de nombres](../../programming-guide/namespaces/using-namespaces.md)
