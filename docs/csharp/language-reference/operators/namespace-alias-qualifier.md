---
title: 'Operador :: (referencia de C#)'
ms.custom: seodec18
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
ms.openlocfilehash: 2aceb51747708b12fb3059b097b72206c78a9d5d
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2019
ms.locfileid: "68971239"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="55826-102">Operador :: (referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="55826-102">:: operator (C# reference)</span></span>

<span data-ttu-id="55826-103">Use el calificador de alias de espacio de nombres `::` para tener acceso a los miembros del espacio de nombres con alias.</span><span class="sxs-lookup"><span data-stu-id="55826-103">Use the namespace alias qualifier `::` to access members of an aliased namespace.</span></span> <span data-ttu-id="55826-104">El calificador `::` se usa entre dos identificadores.</span><span class="sxs-lookup"><span data-stu-id="55826-104">You use the `::` qualifier between two identifiers.</span></span> <span data-ttu-id="55826-105">El identificador de la izquierda puede ser cualquiera de los siguientes alias:</span><span class="sxs-lookup"><span data-stu-id="55826-105">The left-hand identifier can be any of the following aliases:</span></span>

- <span data-ttu-id="55826-106">Un alias de espacio de nombres creado con la [directiva de alias using](../keywords/using-directive.md):</span><span class="sxs-lookup"><span data-stu-id="55826-106">A namespace alias created with the [using alias directive](../keywords/using-directive.md):</span></span>
  
  ```csharp
  using forwinforms = System.Drawing;
  using forwpf = System.Windows;
  
  public class Converters
  {
      public static forwpf::Point Convert(forwinforms::Point point) => new forwpf::Point(point.X, point.Y);
  }
  ```

- <span data-ttu-id="55826-107">Un [alias externo](../keywords/extern-alias.md).</span><span class="sxs-lookup"><span data-stu-id="55826-107">An [extern alias](../keywords/extern-alias.md).</span></span>
- <span data-ttu-id="55826-108">El alias `global`, que es el alias del espacio de nombres global.</span><span class="sxs-lookup"><span data-stu-id="55826-108">The `global` alias, which is the global namespace alias.</span></span> <span data-ttu-id="55826-109">El espacio de nombres global es el espacio de nombres que contiene los espacios de nombres y los tipos que no se declaran dentro de un espacio de nombres con nombre.</span><span class="sxs-lookup"><span data-stu-id="55826-109">The global namespace is the namespace that contains namespaces and types that are not declared inside a named namespace.</span></span> <span data-ttu-id="55826-110">Cuando se usa con el calificador `::`, el alias `global` siempre hace referencia al espacio de nombres global, incluso si está el alias del espacio de nombres `global` definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="55826-110">When used with the `::` qualifier, the `global` alias always references the global namespace, even if there is the user-defined `global` namespace alias.</span></span>
  
  <span data-ttu-id="55826-111">En el ejemplo siguiente se usa el alias `global` para tener acceso al espacio de nombres <xref:System> de .NET, que es miembro del espacio de nombres global.</span><span class="sxs-lookup"><span data-stu-id="55826-111">The following example uses the `global` alias to access the .NET <xref:System> namespace, which is a member of the global namespace.</span></span> <span data-ttu-id="55826-112">Sin el alias `global`, se tendría acceso al espacio de nombres `System` definido por el usuario, que es miembro del espacio de nombres `MyCompany.MyProduct`:</span><span class="sxs-lookup"><span data-stu-id="55826-112">Without the `global` alias, the user-defined `System` namespace, which is a member of the `MyCompany.MyProduct` namespace, would be accessed:</span></span>

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
  > <span data-ttu-id="55826-113">La palabra clave `global` es el alias de espacio de nombres global solo cuando es el identificador izquierdo del calificador `::`.</span><span class="sxs-lookup"><span data-stu-id="55826-113">The `global` keyword is the global namespace alias only when it's the left-hand identifier of the `::` qualifier.</span></span>

<span data-ttu-id="55826-114">También puede usar el [operador de acceso a miembros `.`](member-access-operators.md#member-access-operator-) para acceder a los miembros de un espacio de nombres con alias.</span><span class="sxs-lookup"><span data-stu-id="55826-114">You can also use the [member access `.` operator](member-access-operators.md#member-access-operator-) to access members of an aliased namespace.</span></span> <span data-ttu-id="55826-115">Sin embargo, el operador `.` también se usa para tener acceso a los miembros de un tipo.</span><span class="sxs-lookup"><span data-stu-id="55826-115">However, the `.` operator is also used to access members of a type.</span></span> <span data-ttu-id="55826-116">El calificador `::` garantiza que el identificador de la izquierda siempre hace referencia a un alias de espacio de nombres, aunque exista un tipo o un espacio de nombres con el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="55826-116">The `::` qualifier ensures that its left-hand identifier always references a namespace alias, even if there exists a type or namespace with the same name.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="55826-117">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="55826-117">C# language specification</span></span>

<span data-ttu-id="55826-118">Para más información, consulte la sección sobre [calificadores de alias de espacio de nombres](~/_csharplang/spec/namespaces.md#namespace-alias-qualifiers) de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="55826-118">For more information, see the [Namespace alias qualifiers](~/_csharplang/spec/namespaces.md#namespace-alias-qualifiers) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="55826-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="55826-119">See also</span></span>

- [<span data-ttu-id="55826-120">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="55826-120">C# reference</span></span>](../index.md)
- [<span data-ttu-id="55826-121">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="55826-121">C# operators</span></span>](index.md)
- [<span data-ttu-id="55826-122">Uso de espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="55826-122">Using namespaces</span></span>](../../programming-guide/namespaces/using-namespaces.md)
