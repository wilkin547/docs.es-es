---
title: 'Cómo: Crear objetos GenericPrincipal y GenericIdentity'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Creating Generic Identity Objects
- GenericPrincipal Objects
- Creating GenericPrincipal Objects
- GenericIdentity Objects
ms.assetid: 465694cf-258b-4747-9dae-35b01a5bcdbb
ms.openlocfilehash: 546b4d20f7b6b7a8c448f704fefd9a39b3ebd1d7
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706154"
---
# <a name="how-to-create-genericprincipal-and-genericidentity-objects"></a><span data-ttu-id="28322-102">Cómo: Crear objetos GenericPrincipal y GenericIdentity</span><span class="sxs-lookup"><span data-stu-id="28322-102">How to: Create GenericPrincipal and GenericIdentity Objects</span></span>

<span data-ttu-id="28322-103">Puede usar la clase <xref:System.Security.Principal.GenericIdentity> junto con la <xref:System.Security.Principal.GenericPrincipal> clase para crear un esquema de autorización que exista de manera independiente de un dominio de Windows.</span><span class="sxs-lookup"><span data-stu-id="28322-103">You can use the <xref:System.Security.Principal.GenericIdentity> class in conjunction with the <xref:System.Security.Principal.GenericPrincipal> class to create an authorization scheme that exists independent of a Windows domain.</span></span>

### <a name="to-create-a-genericprincipal-object"></a><span data-ttu-id="28322-104">Para crear un objeto GenericPrincipal</span><span class="sxs-lookup"><span data-stu-id="28322-104">To create a GenericPrincipal object</span></span>

1. <span data-ttu-id="28322-105">Cree una nueva instancia de la clase de identidad e inicialícela con el nombre que desee conservar.</span><span class="sxs-lookup"><span data-stu-id="28322-105">Create a new instance of the identity class and initialize it with the name you want it to hold.</span></span> <span data-ttu-id="28322-106">El código siguiente crea un nuevo objeto **GenericIdentity** y lo inicializa con el nombre `MyUser`.</span><span class="sxs-lookup"><span data-stu-id="28322-106">The following code creates a new **GenericIdentity** object and initializes it with the name `MyUser`.</span></span>

    ```vb
    Dim myIdentity As New GenericIdentity("MyUser")
    ```

    ```csharp
    GenericIdentity myIdentity = new GenericIdentity("MyUser");
    ```

2. <span data-ttu-id="28322-107">Cree una nueva instancia de la clase **GenericPrincipal** e inicialícela con el objeto **GenericIdentity** creado previamente y una matriz de cadenas que representan los roles que desee asociar a esta entidad de seguridad.</span><span class="sxs-lookup"><span data-stu-id="28322-107">Create a new instance of the **GenericPrincipal** class and initialize it with the previously created **GenericIdentity** object and an array of strings that represent the roles that you want associated with this principal.</span></span> <span data-ttu-id="28322-108">En el ejemplo de código siguiente se especifica una matriz de cadenas que representa un rol de administrador y un rol de usuario.</span><span class="sxs-lookup"><span data-stu-id="28322-108">The following code example specifies an array of strings that represent an administrator role and a user role.</span></span> <span data-ttu-id="28322-109">**GenericPrincipal** se inicializa con el **GenericIdentity** anterior y la matriz de cadenas.</span><span class="sxs-lookup"><span data-stu-id="28322-109">The **GenericPrincipal** is then initialized with the previous **GenericIdentity** and the string array.</span></span>

    ```vb
    Dim myStringArray As String() = {"Manager", "Teller"}
    DIm myPrincipal As New GenericPrincipal(myIdentity, myStringArray)
    ```

    ```csharp
    String[] myStringArray = {"Manager", "Teller"};
    GenericPrincipal myPrincipal = new GenericPrincipal(myIdentity, myStringArray);
    ```

3. <span data-ttu-id="28322-110">Utilice el código siguiente para asociar la entidad de seguridad al subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="28322-110">Use the following code to attach the principal to the current thread.</span></span> <span data-ttu-id="28322-111">Esto es útil en situaciones en las que la entidad de seguridad debe validarse varias veces, debe ser validada por otro código que se ejecute en la aplicación o debe validarse mediante un objeto <xref:System.Security.Permissions.PrincipalPermission>.</span><span class="sxs-lookup"><span data-stu-id="28322-111">This is valuable in situations where the principal must be validated several times, it must be validated by other code running in your application, or it must be validated by a <xref:System.Security.Permissions.PrincipalPermission> object.</span></span> <span data-ttu-id="28322-112">Todavía puede realizar la validación basada en roles en el objeto principal sin asociarlo al subproceso.</span><span class="sxs-lookup"><span data-stu-id="28322-112">You can still perform role-based validation on the principal object without attaching it to the thread.</span></span> <span data-ttu-id="28322-113">Para más información, consulte [Reemplazar un objeto Principal](../../../docs/standard/security/replacing-a-principal-object.md).</span><span class="sxs-lookup"><span data-stu-id="28322-113">For more information, see [Replacing a Principal Object](../../../docs/standard/security/replacing-a-principal-object.md).</span></span>

    ```vb
    Thread.CurrentPrincipal = myPrincipal
    ```

    ```csharp
    Thread.CurrentPrincipal = myPrincipal;
    ```

## <a name="example"></a><span data-ttu-id="28322-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="28322-114">Example</span></span>

<span data-ttu-id="28322-115">En el ejemplo de código siguiente se muestra cómo crear una instancia de **GenericPrincipal** y **GenericIdentity**.</span><span class="sxs-lookup"><span data-stu-id="28322-115">The following code example demonstrates how to create an instance of a **GenericPrincipal** and a **GenericIdentity**.</span></span> <span data-ttu-id="28322-116">Este código muestra los valores de estos objetos en la consola.</span><span class="sxs-lookup"><span data-stu-id="28322-116">This code displays the values of these objects to the console.</span></span>

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

<span data-ttu-id="28322-117">Cuando se ejecuta, la aplicación muestra un resultado similar al siguiente.</span><span class="sxs-lookup"><span data-stu-id="28322-117">When executed, the application displays output similar to the following.</span></span>

```console
The Name is: MyIdentity
The IsAuthenticated is: True
Is this a Manager? True
```

## <a name="see-also"></a><span data-ttu-id="28322-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="28322-118">See also</span></span>

- <xref:System.Security.Principal.GenericIdentity>
- <xref:System.Security.Principal.GenericPrincipal>
- <xref:System.Security.Permissions.PrincipalPermission>
- [<span data-ttu-id="28322-119">Reemplazar un objeto Principal</span><span class="sxs-lookup"><span data-stu-id="28322-119">Replacing a Principal Object</span></span>](../../../docs/standard/security/replacing-a-principal-object.md)
- [<span data-ttu-id="28322-120">Objetos Principal e Identity</span><span class="sxs-lookup"><span data-stu-id="28322-120">Principal and Identity Objects</span></span>](../../../docs/standard/security/principal-and-identity-objects.md)
