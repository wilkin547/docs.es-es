---
description: "Más información sobre: BC30686: el acceso a la propiedad predeterminada es ambiguo entre los miembros heredados de la interfaz ' <defaultpropertyname> ' de la interfaz ' <interfacename1> ' y ' <defaultpropertyname> ' de la interfaz '<interfacename2>"
title: Hay un acceso de propiedad Default ambiguo entre los miembros <defaultpropertyname> heredados de la interfaz <interfacename1> y <defaultpropertyname> de la interfaz <interfacename2>
ms.date: 07/20/2015
f1_keywords:
- vbc30686
- bc30686
helpviewer_keywords:
- BC30686
ms.assetid: 784fefec-ef57-48cf-b960-957df419b439
ms.openlocfilehash: 5ae5e5b2dc7a61540e26d125e960d4755141d975
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796657"
---
# <a name="bc30686-default-property-access-is-ambiguous-between-the-inherited-interface-members-defaultpropertyname-of-interface-interfacename1-and-defaultpropertyname-of-interface-interfacename2"></a><span data-ttu-id="1aba0-103">BC30686: el acceso a la propiedad predeterminada es ambiguo entre los miembros heredados de la interfaz ' ' \<defaultpropertyname> de la interfaz ' \<interfacename1> ' y ' \<defaultpropertyname> ' de la interfaz ' \<interfacename2> '</span><span class="sxs-lookup"><span data-stu-id="1aba0-103">BC30686: Default property access is ambiguous between the inherited interface members '\<defaultpropertyname>' of interface '\<interfacename1>' and '\<defaultpropertyname>' of interface '\<interfacename2>'</span></span>

<span data-ttu-id="1aba0-104">Una interfaz hereda de dos interfaces, cada una de las cuales declara una propiedad predeterminada con el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="1aba0-104">An interface inherits from two interfaces, each of which declares a default property with the same name.</span></span> <span data-ttu-id="1aba0-105">El compilador no puede resolver un acceso a esta propiedad predeterminada sin calificación.</span><span class="sxs-lookup"><span data-stu-id="1aba0-105">The compiler cannot resolve an access to this default property without qualification.</span></span> <span data-ttu-id="1aba0-106">Esto se ilustra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="1aba0-106">The following example illustrates this.</span></span>

```vb
Public Interface Iface1
    Default Property prop(ByVal arg As Integer) As Integer
End Interface
Public Interface Iface2
    Default Property prop(ByVal arg As Integer) As Integer
End Interface
Public Interface Iface3
    Inherits Iface1, Iface2
End Interface
Public Class testClass
    Public Sub accessDefaultProperty()
        Dim testObj As Iface3
        Dim testInt As Integer = testObj(1)
    End Sub
End Class
```

<span data-ttu-id="1aba0-107">Cuando se especifica `testObj(1)` , el compilador intenta resolverlo en la propiedad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="1aba0-107">When you specify `testObj(1)`, the compiler tries to resolve it to the default property.</span></span> <span data-ttu-id="1aba0-108">Sin embargo, hay dos propiedades predeterminadas posibles debido a las interfaces heredadas, por lo que el compilador señala este error.</span><span class="sxs-lookup"><span data-stu-id="1aba0-108">However, there are two possible default properties because of the inherited interfaces, so the compiler signals this error.</span></span>

<span data-ttu-id="1aba0-109">**Identificador de error:** BC30686</span><span class="sxs-lookup"><span data-stu-id="1aba0-109">**Error ID:** BC30686</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="1aba0-110">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="1aba0-110">To correct this error</span></span>

- <span data-ttu-id="1aba0-111">Evite la herencia de miembros con el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="1aba0-111">Avoid inheriting any members with the same name.</span></span> <span data-ttu-id="1aba0-112">En el ejemplo anterior, si no `testObj` necesita ninguno de los miembros de, por ejemplo, `Iface2` , declárelo como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="1aba0-112">In the preceding example, if `testObj` does not need any of the members of, say, `Iface2`, then declare it as follows:</span></span>

  ```vb
  Dim testObj As Iface1
  ```

  <span data-ttu-id="1aba0-113">O bien</span><span class="sxs-lookup"><span data-stu-id="1aba0-113">\-or-</span></span>

- <span data-ttu-id="1aba0-114">Implemente la interfaz heredada en una clase.</span><span class="sxs-lookup"><span data-stu-id="1aba0-114">Implement the inheriting interface in a class.</span></span> <span data-ttu-id="1aba0-115">A continuación, puede implementar cada una de las propiedades heredadas con nombres diferentes.</span><span class="sxs-lookup"><span data-stu-id="1aba0-115">Then you can implement each of the inherited properties with different names.</span></span> <span data-ttu-id="1aba0-116">Sin embargo, solo uno de ellos puede ser la propiedad predeterminada de la clase de implementación.</span><span class="sxs-lookup"><span data-stu-id="1aba0-116">However, only one of them can be the default property of the implementing class.</span></span> <span data-ttu-id="1aba0-117">Esto se ilustra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="1aba0-117">The following example illustrates this.</span></span>

  ```vb
  Public Class useIface3
      Implements Iface3
      Default Public Property prop1(ByVal arg As Integer) As Integer Implements Iface1.prop
          ' Insert code to define Get and Set procedures for prop1.
      End Property
      Public Property prop2(ByVal arg As Integer) As Integer Implements Iface2.prop
          ' Insert code to define Get and Set procedures for prop2.
      End Property
  End Class
  ```

## <a name="see-also"></a><span data-ttu-id="1aba0-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="1aba0-118">See also</span></span>

- [<span data-ttu-id="1aba0-119">Interfaces</span><span class="sxs-lookup"><span data-stu-id="1aba0-119">Interfaces</span></span>](../../programming-guide/language-features/interfaces/index.md)
