---
title: 'Cambio importante: PrincipalPermissionAttribute está obsoleto como error'
description: Obtenga información sobre el cambio importante de .NET 5 en las bibliotecas básicas de .NET donde el constructor PrincipalPermissionAttribute está obsoleto y genera un error en tiempo de compilación.
ms.date: 11/01/2020
ms.openlocfilehash: 7568883935633e98b884b553efccf50504448b77
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102257237"
---
# <a name="principalpermissionattribute-is-obsolete-as-error"></a>PrincipalPermissionAttribute está obsoleto como error

El constructor <xref:System.Security.Permissions.PrincipalPermissionAttribute> está obsoleto y genera un error en tiempo de compilación. No se puede crear una instancia de este atributo ni aplicarlo a un método.

## <a name="change-description"></a>Descripción del cambio

En .NET Framework y .NET Core, puede anotar métodos con el atributo <xref:System.Security.Permissions.PrincipalPermissionAttribute>. Por ejemplo:

```csharp
[PrincipalPermission(SecurityAction.Demand, Role = "Administrators")]
public void MyMethod()
{
    // Code that should only run when the current user is an administrator.
}
```

A partir de .NET 5, no se puede aplicar el atributo <xref:System.Security.Permissions.PrincipalPermissionAttribute> a un método. El constructor del atributo está obsoleto y genera un error en tiempo de compilación. A diferencia de otras advertencias de obsolescencia, el error no se puede suprimir.

## <a name="reason-for-change"></a>Motivo del cambio

El tipo <xref:System.Security.Permissions.PrincipalPermissionAttribute>, como otros tipos que colocan <xref:System.Security.Permissions.SecurityAttribute> como subclase, forma parte de la infraestructura de seguridad de acceso del código (CAS) de .NET. En .NET Framework 2.x-4.x, el entorno de ejecución aplica anotaciones <xref:System.Security.Permissions.PrincipalPermissionAttribute> a la entrada de método, incluso si la aplicación se ejecuta en un escenario de plena confianza. .NET Core y .NET 5 y posterior no admiten atributos CAS y el entorno de ejecución los omite.

Esta diferencia de comportamiento entre .NET Framework y .NET Core y .NET 5 puede dar lugar a un escenario de "error de apertura", en el que se debería haber bloqueado el acceso pero, por el contrario, se ha permitido. Para evitar el escenario de "error de apertura", ya no se puede aplicar el atributo en el código que tiene como destino .NET 5 o posterior.

## <a name="version-introduced"></a>Versión introducida

5.0

## <a name=""></a><a id="permission-action">Acción recomendada</a>

Si se produce el error de obsolescencia, debe tomar medidas.

- **Si va a aplicar el atributo a un método de acción de MVC de ASP.NET:**

  Considere la posibilidad de usar la infraestructura de autorización integrada de ASP.NET. En el código siguiente se muestra cómo anotar un controlador con un atributo <xref:System.Web.Mvc.AuthorizeAttribute>. El entorno de ejecución de ASP.NET autoriza al usuario antes de realizar la acción.

  ```csharp
  using Microsoft.AspNetCore.Authorization;

  namespace MySampleApp
  {
      [Authorize(Roles = "Administrator")]
      public class AdministrationController : Controller
      {
          public ActionResult MyAction()
          {
              // This code won't run unless the current user
              // is in the 'Administrator' role.
          }
      }
  }
  ```

  Para obtener más información, vea [Autorización basada en roles en ASP.NET Core](/aspnet/core/security/authorization/roles) e [Introducción a la autorización en ASP.NET Core](/aspnet/core/security/authorization/introduction).

- **Si va a aplicar el atributo a código de biblioteca fuera del contexto de una aplicación web:**

  Realice las comprobaciones manualmente al principio del método. Esto se puede hacer con el método <xref:System.Security.Principal.IPrincipal.IsInRole(System.String)?displayProperty=nameWithType>.

  ```csharp
  using System.Threading;

  void DoSomething()
  {
      if (Thread.CurrentPrincipal == null
          || !Thread.CurrentPrincipal.IsInRole("Administrators"))
      {
          throw new Exception("User is anonymous or isn't an admin.");
      }

      // Code that should run only when user is an administrator.
  }
  ```

## <a name="affected-apis"></a>API afectadas

- <xref:System.Security.Permissions.PrincipalPermissionAttribute?displayProperty=fullName>

<!--

#### Category

- Core .NET libraries
- Security

### Affected APIs

- `T:System.Security.Permissions.PrincipalPermissionAttribute`

-->
