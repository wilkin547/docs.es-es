---
title: Peticiones de vínculos
description: Lea acerca de las peticiones de vínculo, que producen una comprobación de seguridad durante la compilación Just-in-Time (JIT) y examine solo el ensamblado de llamada inmediato del código.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [.NET Framework], demands
- demanded permissions
- permissions [.NET Framework], demands
- granting permissions, demands
- code access security, demands
- user demands for permission
- caller security checks
- link demands
ms.assetid: a33fd5f9-2de9-4653-a4f0-d9df25082c4d
ms.openlocfilehash: 7f5475d5bfff8cc3c500f95b05d54daacc9b253e
ms.sourcegitcommit: c37e8d4642fef647ebab0e1c618ecc29ddfe2a0f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "87855795"
---
# <a name="link-demands"></a><span data-ttu-id="c83b0-103">Peticiones de vínculos</span><span class="sxs-lookup"><span data-stu-id="c83b0-103">Link Demands</span></span>

[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
 <span data-ttu-id="c83b0-104">Una petición de vínculo hace que se produzca una comprobación de seguridad durante la compilación Just-In-Time y comprueba solo el ensamblado de llamada inmediato del código.</span><span class="sxs-lookup"><span data-stu-id="c83b0-104">A link demand causes a security check during just-in-time compilation and checks only the immediate calling assembly of your code.</span></span> <span data-ttu-id="c83b0-105">La vinculación se produce cuando el código se enlaza a una referencia de tipo, incluidas las referencias del puntero de función y las llamadas a métodos.</span><span class="sxs-lookup"><span data-stu-id="c83b0-105">Linking occurs when your code is bound to a type reference, including function pointer references and method calls.</span></span> <span data-ttu-id="c83b0-106">Si el ensamblado de llamada no tiene permisos suficientes para vincularse al código, no se permitirá el vínculo y se producirá una excepción en tiempo de ejecución cuando se cargue y ejecute el código.</span><span class="sxs-lookup"><span data-stu-id="c83b0-106">If the calling assembly does not have sufficient permission to link to your code, the link is not allowed and a runtime exception is thrown when the code is loaded and run.</span></span> <span data-ttu-id="c83b0-107">Las peticiones de vínculo pueden reemplazarse en las clases que heredan de su código.</span><span class="sxs-lookup"><span data-stu-id="c83b0-107">Link demands can be overridden in classes that inherit from your code.</span></span>  
  
 <span data-ttu-id="c83b0-108">No se realiza un recorrido de pila completo con este tipo de demanda y el código sigue siendo susceptible a ataques señuelo.</span><span class="sxs-lookup"><span data-stu-id="c83b0-108">A full stack walk is not performed with this type of demand and that your code is still susceptible to luring attacks.</span></span> <span data-ttu-id="c83b0-109">Por ejemplo, si un método del ensamblado A está protegido por una petición de vínculo, se evalúa un llamador directo en el ensamblado B en función de los permisos del ensamblado B.  Sin embargo, la petición de vínculo no evaluará un método en el ensamblado C si llama indirectamente al método en el ensamblado A utilizando el método en el ensamblado B. La petición de vínculo especifica solo los permisos que los llamadores directos en el ensamblado de llamada inmediato deben tener para vincularse al código.</span><span class="sxs-lookup"><span data-stu-id="c83b0-109">For example, if a method in assembly A is protected by a link demand, a direct caller in assembly B is evaluated based on the permissions of Assembly B.  However, the link demand will not evaluate a method in assembly C if it indirectly calls the method in assembly A using the method in assembly B. The link demand specifies only the permissions direct callers in the immediate calling assembly must have to link to your code.</span></span> <span data-ttu-id="c83b0-110">No especifica los permisos que deben tener todos los llamadores para ejecutar el código.</span><span class="sxs-lookup"><span data-stu-id="c83b0-110">It does not specify the permissions all callers must have to run your code.</span></span>  
  
 <span data-ttu-id="c83b0-111">Los modificadores de recorrido de pila <xref:System.Security.CodeAccessPermission.Assert%2A>, <xref:System.Security.CodeAccessPermission.Deny%2A> y <xref:System.Security.CodeAccessPermission.PermitOnly%2A> no afectan a la evaluación de las peticiones de vínculo.</span><span class="sxs-lookup"><span data-stu-id="c83b0-111">The <xref:System.Security.CodeAccessPermission.Assert%2A>, <xref:System.Security.CodeAccessPermission.Deny%2A>, and <xref:System.Security.CodeAccessPermission.PermitOnly%2A> stack walk modifiers do not affect the evaluation of link demands.</span></span>  <span data-ttu-id="c83b0-112">Dado que las peticiones de vínculo no efectúan ningún recorrido de pila, los modificadores de recorrido de pila no tienen ningún efecto sobre las peticiones de vínculo.</span><span class="sxs-lookup"><span data-stu-id="c83b0-112">Because link demands do not perform a stack walk, the stack walk modifiers have no effect on link demands.</span></span>  
  
 <span data-ttu-id="c83b0-113">Si se tiene acceso a un método protegido por una petición de vínculo a través de la [reflexión](../reflection-and-codedom/reflection.md), una petición de vínculo comprueba el llamador inmediato del código al que se tiene acceso mediante reflexión.</span><span class="sxs-lookup"><span data-stu-id="c83b0-113">If a method protected by a link demand is accessed through [Reflection](../reflection-and-codedom/reflection.md), then a link demand checks the immediate caller of the code accessed through reflection.</span></span> <span data-ttu-id="c83b0-114">Esto es válido tanto para la detección de métodos como para la invocación de métodos efectuados por reflexión.</span><span class="sxs-lookup"><span data-stu-id="c83b0-114">This is true both for method discovery and for method invocation performed using reflection.</span></span> <span data-ttu-id="c83b0-115">Por ejemplo, supongamos que el código usa la reflexión para devolver un <xref:System.Reflection.MethodInfo> objeto que representa un método protegido por una petición de vínculo y, a continuación, pasa ese objeto **MethodInfo** a otro código que usa el objeto para invocar el método original.</span><span class="sxs-lookup"><span data-stu-id="c83b0-115">For example, suppose code uses reflection to return a <xref:System.Reflection.MethodInfo> object representing a method protected by a link demand and then passes that **MethodInfo** object to some other code that uses the object to invoke the original method.</span></span> <span data-ttu-id="c83b0-116">En este caso, la comprobación de la petición de vínculo se produce dos veces: una vez para el código que devuelve el objeto **MethodInfo** y otra para el código que lo invoca.</span><span class="sxs-lookup"><span data-stu-id="c83b0-116">In this case, the link demand check occurs twice: once for the code that returns the **MethodInfo** object and once for the code that invokes it.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c83b0-117">Una petición de vínculo efectuada en un constructor de clases estáticas no protege el constructor, puesto que el sistema llama a los constructores estáticos, fuera de la ruta de acceso de ejecución del código de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c83b0-117">A link demand performed on a static class constructor does not protect the constructor because static constructors are called by the system, outside the application's code execution path.</span></span> <span data-ttu-id="c83b0-118">Como resultado, al aplicar una petición de vínculo a toda una clase, no puede proteger el acceso a un constructor estático, aunque proteja el resto de la clase.</span><span class="sxs-lookup"><span data-stu-id="c83b0-118">As a result, when a link demand is applied to an entire class, it cannot protect access to a static constructor, although it does protect the rest of the class.</span></span>  
  
 <span data-ttu-id="c83b0-119">El siguiente fragmento de código especifica de manera declarativa que cualquier código vinculado al método `ReadData` debe tener el permiso `CustomPermission`.</span><span class="sxs-lookup"><span data-stu-id="c83b0-119">The following code fragment declaratively specifies that any code linking to the `ReadData` method must have the `CustomPermission` permission.</span></span> <span data-ttu-id="c83b0-120">Este permiso es un permiso personalizado hipotético y no existe en .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c83b0-120">This permission is a hypothetical custom permission and does not exist in the .NET Framework.</span></span> <span data-ttu-id="c83b0-121">La petición se realiza pasando una marca **SecurityAction. LinkDemand** a `CustomPermissionAttribute` .</span><span class="sxs-lookup"><span data-stu-id="c83b0-121">The demand is made by passing a **SecurityAction.LinkDemand** flag to the `CustomPermissionAttribute`.</span></span>  
  
```vb  
<CustomPermissionAttribute(SecurityAction.LinkDemand)> _  
Public Shared Function ReadData() As String  
    ' Access a custom resource.  
End Function
```  
  
```csharp  
[CustomPermissionAttribute(SecurityAction.LinkDemand)]  
public static string ReadData()  
{  
    // Access a custom resource.  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="c83b0-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="c83b0-122">See also</span></span>

- [<span data-ttu-id="c83b0-123">Atributos</span><span class="sxs-lookup"><span data-stu-id="c83b0-123">Attributes</span></span>](../../standard/attributes/index.md)
- [<span data-ttu-id="c83b0-124">Seguridad de acceso del código</span><span class="sxs-lookup"><span data-stu-id="c83b0-124">Code Access Security</span></span>](code-access-security.md)
