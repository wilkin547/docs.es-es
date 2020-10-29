---
title: Error SYSLIB0002
description: Obtenga información sobre la obsolescencia que genera el error en tiempo de compilación SYSLIB0002.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: 00fd42975c9286221b75c87caef8d2109b9b7100
ms.sourcegitcommit: dfcbc096ad7908cd58a5f0aeabd2256f05266bac
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2020
ms.locfileid: "92333184"
---
# <a name="syslib0002-principalpermissionattribute-is-obsolete"></a>SYSLIB0002: PrincipalPermissionAttribute está obsoleto

El constructor <xref:System.Security.Permissions.PrincipalPermissionAttribute> está obsoleto y genera un error en tiempo de compilación`SYSLIB0002` a partir de .NET 5.0. No se puede crear una instancia de este atributo ni aplicarlo a un método.

A diferencia de otras advertencias de obsolescencia, el error no se puede suprimir.

## <a name="workarounds"></a>Soluciones alternativas

- Si va a aplicar el atributo a un método de acción de MVC de ASP.NET:

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

- Si va a aplicar el atributo a código de biblioteca fuera del contexto de una aplicación web:

  Realice las comprobaciones manualmente al principio del método mediante una llamada al método <xref:System.Security.Principal.IPrincipal.IsInRole(System.String)?displayProperty=nameWithType>.

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

## <a name="see-also"></a>Vea también

- [PrincipalPermissionAttribute está obsoleto como error](3.1-5.0.md#principalpermissionattribute-is-obsolete-as-error)
