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
# <a name="how-to-create-genericprincipal-and-genericidentity-objects"></a>Procedimiento para crear objetos GenericPrincipal y GenericIdentity

> [!NOTE]
> Este artículo se aplica a Windows.
>
> Para obtener información sobre ASP.NET Core, consulte [información general sobre la seguridad de ASP.net Core](/aspnet/core/security/).

Puede utilizar la <xref:System.Security.Principal.GenericIdentity> clase junto con la <xref:System.Security.Principal.GenericPrincipal> clase para crear un esquema de autorización que exista de manera independiente de un dominio de Windows.

### <a name="to-create-a-genericprincipal-object"></a>Para crear un objeto GenericPrincipal

1. Cree una nueva instancia de la clase de identidad e inicialícela con el nombre que desee conservar. El código siguiente crea un nuevo objeto **GenericIdentity** y lo inicializa con el nombre `MyUser`.

    ```vb
    Dim myIdentity As New GenericIdentity("MyUser")
    ```

    ```csharp
    GenericIdentity myIdentity = new GenericIdentity("MyUser");
    ```

2. Cree una nueva instancia de la clase **GenericPrincipal** e inicialícela con el objeto **GenericIdentity** creado previamente y una matriz de cadenas que representan los roles que desee asociar a esta entidad de seguridad. En el ejemplo de código siguiente se especifica una matriz de cadenas que representa un rol de administrador y un rol de usuario. **GenericPrincipal** se inicializa con el **GenericIdentity** anterior y la matriz de cadenas.

    ```vb
    Dim myStringArray As String() = {"Manager", "Teller"}
    DIm myPrincipal As New GenericPrincipal(myIdentity, myStringArray)
    ```

    ```csharp
    String[] myStringArray = {"Manager", "Teller"};
    GenericPrincipal myPrincipal = new GenericPrincipal(myIdentity, myStringArray);
    ```

3. Utilice el código siguiente para asociar la entidad de seguridad al subproceso actual. Esto es útil en situaciones en las que la entidad de seguridad debe validarse varias veces, debe ser validada por otro código que se ejecute en la aplicación o debe ser validada por un <xref:System.Security.Permissions.PrincipalPermission> objeto. Todavía puede realizar la validación basada en roles en el objeto principal sin asociarlo al subproceso. Para más información, consulte [Reemplazar un objeto Principal](replacing-a-principal-object.md).

    ```vb
    Thread.CurrentPrincipal = myPrincipal
    ```

    ```csharp
    Thread.CurrentPrincipal = myPrincipal;
    ```

## <a name="example"></a>Ejemplo

En el ejemplo de código siguiente se muestra cómo crear una instancia de **GenericPrincipal** y **GenericIdentity**. Este código muestra los valores de estos objetos en la consola.

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

Cuando se ejecuta, la aplicación muestra un resultado similar al siguiente.

```console
The Name is: MyIdentity
The IsAuthenticated is: True
Is this a Manager? True
```

## <a name="see-also"></a>Vea también

- <xref:System.Security.Principal.GenericIdentity>
- <xref:System.Security.Principal.GenericPrincipal>
- <xref:System.Security.Permissions.PrincipalPermission>
- [Reemplazar un objeto Principal](replacing-a-principal-object.md)
- [Objetos Principal e Identity](principal-and-identity-objects.md)
