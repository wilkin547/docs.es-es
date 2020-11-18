---
title: Procedimiento para crear objetos GenericPrincipal y GenericIdentity
ms.date: 07/15/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Creating Generic Identity Objects
- GenericPrincipal Objects
- Creating GenericPrincipal Objects
- GenericIdentity Objects
ms.assetid: 465694cf-258b-4747-9dae-35b01a5bcdbb
ms.openlocfilehash: cde4669a1bac49d1d9fde39c99707561379aec19
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94818998"
---
# <a name="how-to-create-genericprincipal-and-genericidentity-objects"></a><span data-ttu-id="5c6ea-102">Procedimiento para crear objetos GenericPrincipal y GenericIdentity</span><span class="sxs-lookup"><span data-stu-id="5c6ea-102">How to: Create GenericPrincipal and GenericIdentity Objects</span></span>

> [!NOTE]
> <span data-ttu-id="5c6ea-103">Este artículo se aplica a Windows.</span><span class="sxs-lookup"><span data-stu-id="5c6ea-103">This article applies to Windows.</span></span>
>
> <span data-ttu-id="5c6ea-104">Para obtener información sobre ASP.NET Core, consulte [información general sobre la seguridad de ASP.net Core](/aspnet/core/security/).</span><span class="sxs-lookup"><span data-stu-id="5c6ea-104">For information about ASP.NET Core, see [Overview of ASP.NET Core Security](/aspnet/core/security/).</span></span>

<span data-ttu-id="5c6ea-105">Puede utilizar la <xref:System.Security.Principal.GenericIdentity> clase junto con la <xref:System.Security.Principal.GenericPrincipal> clase para crear un esquema de autorización que exista de manera independiente de un dominio de Windows.</span><span class="sxs-lookup"><span data-stu-id="5c6ea-105">You can use the <xref:System.Security.Principal.GenericIdentity> class in conjunction with the <xref:System.Security.Principal.GenericPrincipal> class to create an authorization scheme that exists independent of a Windows domain.</span></span>

### <a name="to-create-a-genericprincipal-object"></a><span data-ttu-id="5c6ea-106">Para crear un objeto GenericPrincipal</span><span class="sxs-lookup"><span data-stu-id="5c6ea-106">To create a GenericPrincipal object</span></span>

1. <span data-ttu-id="5c6ea-107">Cree una nueva instancia de la clase de identidad e inicialícela con el nombre que desee conservar.</span><span class="sxs-lookup"><span data-stu-id="5c6ea-107">Create a new instance of the identity class and initialize it with the name you want it to hold.</span></span> <span data-ttu-id="5c6ea-108">El código siguiente crea un nuevo objeto **GenericIdentity** y lo inicializa con el nombre `MyUser`.</span><span class="sxs-lookup"><span data-stu-id="5c6ea-108">The following code creates a new **GenericIdentity** object and initializes it with the name `MyUser`.</span></span>

    ```vb
    Dim myIdentity As New GenericIdentity("MyUser")
    ```

    ```csharp
    GenericIdentity myIdentity = new GenericIdentity("MyUser");
    ```

2. <span data-ttu-id="5c6ea-109">Cree una nueva instancia de la clase **GenericPrincipal** e inicialícela con el objeto **GenericIdentity** creado previamente y una matriz de cadenas que representan los roles que desee asociar a esta entidad de seguridad.</span><span class="sxs-lookup"><span data-stu-id="5c6ea-109">Create a new instance of the **GenericPrincipal** class and initialize it with the previously created **GenericIdentity** object and an array of strings that represent the roles that you want associated with this principal.</span></span> <span data-ttu-id="5c6ea-110">En el ejemplo de código siguiente se especifica una matriz de cadenas que representa un rol de administrador y un rol de usuario.</span><span class="sxs-lookup"><span data-stu-id="5c6ea-110">The following code example specifies an array of strings that represent an administrator role and a user role.</span></span> <span data-ttu-id="5c6ea-111">**GenericPrincipal** se inicializa con el **GenericIdentity** anterior y la matriz de cadenas.</span><span class="sxs-lookup"><span data-stu-id="5c6ea-111">The **GenericPrincipal** is then initialized with the previous **GenericIdentity** and the string array.</span></span>

    ```vb
    Dim myStringArray As String() = {"Manager", "Teller"}
    DIm myPrincipal As New GenericPrincipal(myIdentity, myStringArray)
    ```

    ```csharp
    String[] myStringArray = {"Manager", "Teller"};
    GenericPrincipal myPrincipal = new GenericPrincipal(myIdentity, myStringArray);
    ```

3. <span data-ttu-id="5c6ea-112">Utilice el código siguiente para asociar la entidad de seguridad al subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="5c6ea-112">Use the following code to attach the principal to the current thread.</span></span> <span data-ttu-id="5c6ea-113">Esto es útil en situaciones en las que la entidad de seguridad debe validarse varias veces, debe ser validada por otro código que se ejecute en la aplicación o debe ser validada por un <xref:System.Security.Permissions.PrincipalPermission> objeto.</span><span class="sxs-lookup"><span data-stu-id="5c6ea-113">This is valuable in situations where the principal must be validated several times, it must be validated by other code running in your application, or it must be validated by a <xref:System.Security.Permissions.PrincipalPermission> object.</span></span> <span data-ttu-id="5c6ea-114">Todavía puede realizar la validación basada en roles en el objeto principal sin asociarlo al subproceso.</span><span class="sxs-lookup"><span data-stu-id="5c6ea-114">You can still perform role-based validation on the principal object without attaching it to the thread.</span></span> <span data-ttu-id="5c6ea-115">Para más información, consulte [Reemplazar un objeto Principal](replacing-a-principal-object.md).</span><span class="sxs-lookup"><span data-stu-id="5c6ea-115">For more information, see [Replacing a Principal Object](replacing-a-principal-object.md).</span></span>

    ```vb
    Thread.CurrentPrincipal = myPrincipal
    ```

    ```csharp
    Thread.CurrentPrincipal = myPrincipal;
    ```

## <a name="example"></a><span data-ttu-id="5c6ea-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5c6ea-116">Example</span></span>

<span data-ttu-id="5c6ea-117">En el ejemplo de código siguiente se muestra cómo crear una instancia de **GenericPrincipal** y **GenericIdentity**.</span><span class="sxs-lookup"><span data-stu-id="5c6ea-117">The following code example demonstrates how to create an instance of a **GenericPrincipal** and a **GenericIdentity**.</span></span> <span data-ttu-id="5c6ea-118">Este código muestra los valores de estos objetos en la consola.</span><span class="sxs-lookup"><span data-stu-id="5c6ea-118">This code displays the values of these objects to the console.</span></span>

```vb
Imports System.Security.Principal
Imports System.Threading

Public Class Class1

    Public Shared Sub Main()
        ' Create generic identity.
        Dim myIdentity As New GenericIdentity("MyIdentity")

        ' Create generic principal.
        Dim myStringArray As String() =  {"Manager", "Teller"}
        Dim myPrincipal As New GenericPrincipal(myIdentity, myStringArray)

        ' Attach the principal to the current thread.
        ' This is not required unless repeated validation must occur,
        ' other code in your application must validate, or the
        ' PrincipalPermission object is used.
        Thread.CurrentPrincipal = myPrincipal

        ' Print values to the console.
        Dim name As String = myPrincipal.Identity.Name
        Dim auth As Boolean = myPrincipal.Identity.IsAuthenticated
        Dim isInRole As Boolean = myPrincipal.IsInRole("Manager")

        Console.WriteLine("The name is: {0}", name)
        Console.WriteLine("The isAuthenticated is: {0}", auth)
        Console.WriteLine("Is this a Manager? {0}", isInRole)

    End Sub

End Class
```

```csharp
using System;
using System.Security.Principal;
using System.Threading;

public class Class1
{
    public static int Main(string[] args)
    {
    // Create generic identity.
    GenericIdentity myIdentity = new GenericIdentity("MyIdentity");

    // Create generic principal.
    String[] myStringArray = {"Manager", "Teller"};
    GenericPrincipal myPrincipal =
        new GenericPrincipal(myIdentity, myStringArray);

    // Attach the principal to the current thread.
    // This is not required unless repeated validation must occur,
    // other code in your application must validate, or the
    // PrincipalPermission object is used.
    Thread.CurrentPrincipal = myPrincipal;

    // Print values to the console.
    String name =  myPrincipal.Identity.Name;
    bool auth =  myPrincipal.Identity.IsAuthenticated;
    bool isInRole =  myPrincipal.IsInRole("Manager");

    Console.WriteLine("The name is: {0}", name);
    Console.WriteLine("The isAuthenticated is: {0}", auth);
    Console.WriteLine("Is this a Manager? {0}", isInRole);

    return 0;
    }
}
```

<span data-ttu-id="5c6ea-119">Cuando se ejecuta, la aplicación muestra un resultado similar al siguiente.</span><span class="sxs-lookup"><span data-stu-id="5c6ea-119">When executed, the application displays output similar to the following.</span></span>

```console
The Name is: MyIdentity
The IsAuthenticated is: True
Is this a Manager? True
```

## <a name="see-also"></a><span data-ttu-id="5c6ea-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="5c6ea-120">See also</span></span>

- <xref:System.Security.Principal.GenericIdentity>
- <xref:System.Security.Principal.GenericPrincipal>
- <xref:System.Security.Permissions.PrincipalPermission>
- [<span data-ttu-id="5c6ea-121">Reemplazar un objeto Principal</span><span class="sxs-lookup"><span data-stu-id="5c6ea-121">Replacing a Principal Object</span></span>](replacing-a-principal-object.md)
- [<span data-ttu-id="5c6ea-122">Objetos Principal e Identity</span><span class="sxs-lookup"><span data-stu-id="5c6ea-122">Principal and Identity Objects</span></span>](principal-and-identity-objects.md)
