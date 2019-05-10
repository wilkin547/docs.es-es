---
title: Hay un acceso de propiedad Default ambiguo entre los miembros <defaultpropertyname> heredados de la interfaz <interfacename1> y <defaultpropertyname> de la interfaz <interfacename2>
ms.date: 07/20/2015
f1_keywords:
- vbc30686
- bc30686
helpviewer_keywords:
- BC30686
ms.assetid: 784fefec-ef57-48cf-b960-957df419b439
ms.openlocfilehash: 99d5dc2e0f8389f8c9e90786c4d9d0fa037eb828
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64651416"
---
# <a name="default-property-access-is-ambiguous-between-the-inherited-interface-members-defaultpropertyname-of-interface-interfacename1-and-defaultpropertyname-of-interface-interfacename2"></a><span data-ttu-id="7342d-102">Acceso a la propiedad predeterminada es ambiguo entre los miembros heredados\<defaultpropertyname >' de interfaz '\<interfacename1 >' y '\<defaultpropertyname >' de interfaz '\< interfacename2 >'</span><span class="sxs-lookup"><span data-stu-id="7342d-102">Default property access is ambiguous between the inherited interface members '\<defaultpropertyname>' of interface '\<interfacename1>' and '\<defaultpropertyname>' of interface '\<interfacename2>'</span></span>
<span data-ttu-id="7342d-103">Una interfaz hereda de dos interfaces, cada una de las cuales declara una propiedad predeterminada con el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="7342d-103">An interface inherits from two interfaces, each of which declares a default property with the same name.</span></span> <span data-ttu-id="7342d-104">El compilador no puede resolver un acceso a esta propiedad predeterminada sin calificación.</span><span class="sxs-lookup"><span data-stu-id="7342d-104">The compiler cannot resolve an access to this default property without qualification.</span></span> <span data-ttu-id="7342d-105">Esto se ilustra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="7342d-105">The following example illustrates this.</span></span>  
  
```  
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
  
 <span data-ttu-id="7342d-106">Cuando se especifica `testObj(1)`, el compilador intenta solucionarlo a la propiedad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="7342d-106">When you specify `testObj(1)`, the compiler tries to resolve it to the default property.</span></span> <span data-ttu-id="7342d-107">Sin embargo, hay dos propiedades predeterminadas posibles debido a las interfaces heredadas, por lo que el compilador señala este error.</span><span class="sxs-lookup"><span data-stu-id="7342d-107">However, there are two possible default properties because of the inherited interfaces, so the compiler signals this error.</span></span>  
  
 <span data-ttu-id="7342d-108">**Identificador de error:** BC30686</span><span class="sxs-lookup"><span data-stu-id="7342d-108">**Error ID:** BC30686</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7342d-109">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="7342d-109">To correct this error</span></span>  
  
- <span data-ttu-id="7342d-110">Evite heredar a miembros con el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="7342d-110">Avoid inheriting any members with the same name.</span></span> <span data-ttu-id="7342d-111">En el ejemplo anterior, si `testObj` no necesita ninguno de los miembros de, digamos, `Iface2`, declárelo como sigue:</span><span class="sxs-lookup"><span data-stu-id="7342d-111">In the preceding example, if `testObj` does not need any of the members of, say, `Iface2`, then declare it as follows:</span></span>  
  
    ```  
    Dim testObj As Iface1  
    ```  
  
     <span data-ttu-id="7342d-112">-o bien-</span><span class="sxs-lookup"><span data-stu-id="7342d-112">-or-</span></span>  
  
- <span data-ttu-id="7342d-113">Implementar la interfaz que hereda de una clase.</span><span class="sxs-lookup"><span data-stu-id="7342d-113">Implement the inheriting interface in a class.</span></span> <span data-ttu-id="7342d-114">A continuación, puede implementar cada una de las propiedades heredadas con nombres diferentes.</span><span class="sxs-lookup"><span data-stu-id="7342d-114">Then you can implement each of the inherited properties with different names.</span></span> <span data-ttu-id="7342d-115">Sin embargo, solo uno de ellos puede ser la propiedad predeterminada de la clase de implementación.</span><span class="sxs-lookup"><span data-stu-id="7342d-115">However, only one of them can be the default property of the implementing class.</span></span> <span data-ttu-id="7342d-116">Esto se ilustra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="7342d-116">The following example illustrates this.</span></span>  
  
    ```  
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
  
## <a name="see-also"></a><span data-ttu-id="7342d-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="7342d-117">See also</span></span>

- [<span data-ttu-id="7342d-118">Interfaces</span><span class="sxs-lookup"><span data-stu-id="7342d-118">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
