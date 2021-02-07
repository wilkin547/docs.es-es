---
description: 'Más información acerca de cómo: crear objetos GenericPrincipal y GenericIdentity'
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
ms.openlocfilehash: 8c77a9afec7bd166a71abb6af19d8766b02d0523
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99685223"
---
# <a name="how-to-create-genericprincipal-and-genericidentity-objects"></a><span data-ttu-id="a7331-103">Procedimiento para crear objetos GenericPrincipal y GenericIdentity</span><span class="sxs-lookup"><span data-stu-id="a7331-103">How to: Create GenericPrincipal and GenericIdentity Objects</span></span>

> [!NOTE]
> <span data-ttu-id="a7331-104">Este artículo se aplica a Windows.</span><span class="sxs-lookup"><span data-stu-id="a7331-104">This article applies to Windows.</span></span>
>
> <span data-ttu-id="a7331-105">Para obtener información sobre ASP.NET Core, consulte [información general sobre la seguridad de ASP.net Core](/aspnet/core/security/).</span><span class="sxs-lookup"><span data-stu-id="a7331-105">For information about ASP.NET Core, see [Overview of ASP.NET Core Security](/aspnet/core/security/).</span></span>

<span data-ttu-id="a7331-106">Puede utilizar la <xref:System.Security.Principal.GenericIdentity> clase junto con la <xref:System.Security.Principal.GenericPrincipal> clase para crear un esquema de autorización que exista de manera independiente de un dominio de Windows.</span><span class="sxs-lookup"><span data-stu-id="a7331-106">You can use the <xref:System.Security.Principal.GenericIdentity> class in conjunction with the <xref:System.Security.Principal.GenericPrincipal> class to create an authorization scheme that exists independent of a Windows domain.</span></span>

### <a name="to-create-a-genericprincipal-object"></a><span data-ttu-id="a7331-107">Para crear un objeto GenericPrincipal</span><span class="sxs-lookup"><span data-stu-id="a7331-107">To create a GenericPrincipal object</span></span>

1. <span data-ttu-id="a7331-108">Cree una nueva instancia de la clase de identidad e inicialícela con el nombre que desee conservar.</span><span class="sxs-lookup"><span data-stu-id="a7331-108">Create a new instance of the identity class and initialize it with the name you want it to hold.</span></span> <span data-ttu-id="a7331-109">El código siguiente crea un nuevo objeto **GenericIdentity** y lo inicializa con el nombre `MyUser`.</span><span class="sxs-lookup"><span data-stu-id="a7331-109">The following code creates a new **GenericIdentity** object and initializes it with the name `MyUser`.</span></span>

    ```vb
    Dim myIdentity As New GenericIdentity("MyUser")
    ```

    ```csharp
    GenericIdentity myIdentity = new GenericIdentity("MyUser");
    ```

2. <span data-ttu-id="a7331-110">Cree una nueva instancia de la clase **GenericPrincipal** e inicialícela con el objeto **GenericIdentity** creado previamente y una matriz de cadenas que representan los roles que desee asociar a esta entidad de seguridad.</span><span class="sxs-lookup"><span data-stu-id="a7331-110">Create a new instance of the **GenericPrincipal** class and initialize it with the previously created **GenericIdentity** object and an array of strings that represent the roles that you want associated with this principal.</span></span> <span data-ttu-id="a7331-111">En el ejemplo de código siguiente se especifica una matriz de cadenas que representa un rol de administrador y un rol de usuario.</span><span class="sxs-lookup"><span data-stu-id="a7331-111">The following code example specifies an array of strings that represent an administrator role and a user role.</span></span> <span data-ttu-id="a7331-112">**GenericPrincipal** se inicializa con el **GenericIdentity** anterior y la matriz de cadenas.</span><span class="sxs-lookup"><span data-stu-id="a7331-112">The **GenericPrincipal** is then initialized with the previous **GenericIdentity** and the string array.</span></span>

    ```vb
    Dim myStringArray As String() = {"Manager", "Teller"}
    DIm myPrincipal As New GenericPrincipal(myIdentity, myStringArray)
    ```

    ```csharp
    String[] myStringArray = {"Manager", "Teller"};
    GenericPrincipal myPrincipal = new GenericPrincipal(myIdentity, myStringArray);
    ```

3. <span data-ttu-id="a7331-113">Utilice el código siguiente para asociar la entidad de seguridad al subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="a7331-113">Use the following code to attach the principal to the current thread.</span></span> <span data-ttu-id="a7331-114">Esto es útil en situaciones en las que la entidad de seguridad debe validarse varias veces, debe ser validada por otro código que se ejecute en la aplicación o debe ser validada por un <xref:System.Security.Permissions.PrincipalPermission> objeto.</span><span class="sxs-lookup"><span data-stu-id="a7331-114">This is valuable in situations where the principal must be validated several times, it must be validated by other code running in your application, or it must be validated by a <xref:System.Security.Permissions.PrincipalPermission> object.</span></span> <span data-ttu-id="a7331-115">Todavía puede realizar la validación basada en roles en el objeto principal sin asociarlo al subproceso.</span><span class="sxs-lookup"><span data-stu-id="a7331-115">You can still perform role-based validation on the principal object without attaching it to the thread.</span></span> <span data-ttu-id="a7331-116">Para más información, consulte [Reemplazar un objeto Principal](replacing-a-principal-object.md).</span><span class="sxs-lookup"><span data-stu-id="a7331-116">For more information, see [Replacing a Principal Object](replacing-a-principal-object.md).</span></span>

    ```vb
    Thread.CurrentPrincipal = myPrincipal
    ```

    ```csharp
    Thread.CurrentPrincipal = myPrincipal;
    ```

## <a name="example"></a><span data-ttu-id="a7331-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a7331-117">Example</span></span>

<span data-ttu-id="a7331-118">En el ejemplo de código siguiente se muestra cómo crear una instancia de **GenericPrincipal** y **GenericIdentity**.</span><span class="sxs-lookup"><span data-stu-id="a7331-118">The following code example demonstrates how to create an instance of a **GenericPrincipal** and a **GenericIdentity**.</span></span> <span data-ttu-id="a7331-119">Este código muestra los valores de estos objetos en la consola.</span><span class="sxs-lookup"><span data-stu-id="a7331-119">This code displays the values of these objects to the console.</span></span>

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

<span data-ttu-id="a7331-120">Cuando se ejecuta, la aplicación muestra un resultado similar al siguiente.</span><span class="sxs-lookup"><span data-stu-id="a7331-120">When executed, the application displays output similar to the following.</span></span>

```console
The Name is: MyIdentity
The IsAuthenticated is: True
Is this a Manager? True
```

## <a name="see-also"></a><span data-ttu-id="a7331-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="a7331-121">See also</span></span>

- <xref:System.Security.Principal.GenericIdentity>
- <xref:System.Security.Principal.GenericPrincipal>
- <xref:System.Security.Permissions.PrincipalPermission>
- [<span data-ttu-id="a7331-122">Reemplazar un objeto Principal</span><span class="sxs-lookup"><span data-stu-id="a7331-122">Replacing a Principal Object</span></span>](replacing-a-principal-object.md)
- [<span data-ttu-id="a7331-123">Objetos Principal e Identity</span><span class="sxs-lookup"><span data-stu-id="a7331-123">Principal and Identity Objects</span></span>](principal-and-identity-objects.md)
