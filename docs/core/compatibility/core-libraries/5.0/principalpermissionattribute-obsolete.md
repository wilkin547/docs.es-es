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
# <a name="principalpermissionattribute-is-obsolete-as-error"></a><span data-ttu-id="6c40f-103">PrincipalPermissionAttribute está obsoleto como error</span><span class="sxs-lookup"><span data-stu-id="6c40f-103">PrincipalPermissionAttribute is obsolete as error</span></span>

<span data-ttu-id="6c40f-104">El constructor <xref:System.Security.Permissions.PrincipalPermissionAttribute> está obsoleto y genera un error en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="6c40f-104">The <xref:System.Security.Permissions.PrincipalPermissionAttribute> constructor is obsolete and produces a compile-time error.</span></span> <span data-ttu-id="6c40f-105">No se puede crear una instancia de este atributo ni aplicarlo a un método.</span><span class="sxs-lookup"><span data-stu-id="6c40f-105">You cannot instantiate this attribute or apply it to a method.</span></span>

## <a name="change-description"></a><span data-ttu-id="6c40f-106">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="6c40f-106">Change description</span></span>

<span data-ttu-id="6c40f-107">En .NET Framework y .NET Core, puede anotar métodos con el atributo <xref:System.Security.Permissions.PrincipalPermissionAttribute>.</span><span class="sxs-lookup"><span data-stu-id="6c40f-107">On .NET Framework and .NET Core, you can annotate methods with the <xref:System.Security.Permissions.PrincipalPermissionAttribute> attribute.</span></span> <span data-ttu-id="6c40f-108">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6c40f-108">For example:</span></span>

```csharp
[PrincipalPermission(SecurityAction.Demand, Role = "Administrators")]
public void MyMethod()
{
    // Code that should only run when the current user is an administrator.
}
```

<span data-ttu-id="6c40f-109">A partir de .NET 5, no se puede aplicar el atributo <xref:System.Security.Permissions.PrincipalPermissionAttribute> a un método.</span><span class="sxs-lookup"><span data-stu-id="6c40f-109">Starting in .NET 5, you cannot apply the <xref:System.Security.Permissions.PrincipalPermissionAttribute> attribute to a method.</span></span> <span data-ttu-id="6c40f-110">El constructor del atributo está obsoleto y genera un error en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="6c40f-110">The constructor for the attribute is obsolete and produces a compile-time error.</span></span> <span data-ttu-id="6c40f-111">A diferencia de otras advertencias de obsolescencia, el error no se puede suprimir.</span><span class="sxs-lookup"><span data-stu-id="6c40f-111">Unlike other obsoletion warnings, you can't suppress the error.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="6c40f-112">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="6c40f-112">Reason for change</span></span>

<span data-ttu-id="6c40f-113">El tipo <xref:System.Security.Permissions.PrincipalPermissionAttribute>, como otros tipos que colocan <xref:System.Security.Permissions.SecurityAttribute> como subclase, forma parte de la infraestructura de seguridad de acceso del código (CAS) de .NET.</span><span class="sxs-lookup"><span data-stu-id="6c40f-113">The <xref:System.Security.Permissions.PrincipalPermissionAttribute> type, like other types that subclass <xref:System.Security.Permissions.SecurityAttribute>, is part of .NET's Code Access Security (CAS) infrastructure.</span></span> <span data-ttu-id="6c40f-114">En .NET Framework 2.x-4.x, el entorno de ejecución aplica anotaciones <xref:System.Security.Permissions.PrincipalPermissionAttribute> a la entrada de método, incluso si la aplicación se ejecuta en un escenario de plena confianza.</span><span class="sxs-lookup"><span data-stu-id="6c40f-114">In .NET Framework 2.x - 4.x, the runtime enforces <xref:System.Security.Permissions.PrincipalPermissionAttribute> annotations on method entry, even if the application is running under a full-trust scenario.</span></span> <span data-ttu-id="6c40f-115">.NET Core y .NET 5 y posterior no admiten atributos CAS y el entorno de ejecución los omite.</span><span class="sxs-lookup"><span data-stu-id="6c40f-115">.NET Core and .NET 5 and later don't support CAS attributes, and the runtime ignores them.</span></span>

<span data-ttu-id="6c40f-116">Esta diferencia de comportamiento entre .NET Framework y .NET Core y .NET 5 puede dar lugar a un escenario de "error de apertura", en el que se debería haber bloqueado el acceso pero, por el contrario, se ha permitido.</span><span class="sxs-lookup"><span data-stu-id="6c40f-116">This difference in behavior from .NET Framework to .NET Core and .NET 5 can result in a "fail open" scenario, where access should have been blocked but instead has been allowed.</span></span> <span data-ttu-id="6c40f-117">Para evitar el escenario de "error de apertura", ya no se puede aplicar el atributo en el código que tiene como destino .NET 5 o posterior.</span><span class="sxs-lookup"><span data-stu-id="6c40f-117">To prevent the "fail open" scenario, you can no longer apply the attribute in code that targets .NET 5 or later.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="6c40f-118">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="6c40f-118">Version introduced</span></span>

<span data-ttu-id="6c40f-119">5.0</span><span class="sxs-lookup"><span data-stu-id="6c40f-119">5.0</span></span>

## <a name=""></a><span data-ttu-id="6c40f-120"><a id="permission-action">Acción recomendada</a></span><span class="sxs-lookup"><span data-stu-id="6c40f-120"><a id="permission-action">Recommended action</a></span></span>

<span data-ttu-id="6c40f-121">Si se produce el error de obsolescencia, debe tomar medidas.</span><span class="sxs-lookup"><span data-stu-id="6c40f-121">If you encounter the obsoletion error, you must take action.</span></span>

- <span data-ttu-id="6c40f-122">**Si va a aplicar el atributo a un método de acción de MVC de ASP.NET:**</span><span class="sxs-lookup"><span data-stu-id="6c40f-122">**If you're applying the attribute to an ASP.NET MVC action method:**</span></span>

  <span data-ttu-id="6c40f-123">Considere la posibilidad de usar la infraestructura de autorización integrada de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="6c40f-123">Consider using ASP.NET's built-in authorization infrastructure.</span></span> <span data-ttu-id="6c40f-124">En el código siguiente se muestra cómo anotar un controlador con un atributo <xref:System.Web.Mvc.AuthorizeAttribute>.</span><span class="sxs-lookup"><span data-stu-id="6c40f-124">The following code demonstrates how to annotate a controller with an <xref:System.Web.Mvc.AuthorizeAttribute> attribute.</span></span> <span data-ttu-id="6c40f-125">El entorno de ejecución de ASP.NET autoriza al usuario antes de realizar la acción.</span><span class="sxs-lookup"><span data-stu-id="6c40f-125">The ASP.NET runtime will authorize the user before performing the action.</span></span>

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

  <span data-ttu-id="6c40f-126">Para obtener más información, vea [Autorización basada en roles en ASP.NET Core](/aspnet/core/security/authorization/roles) e [Introducción a la autorización en ASP.NET Core](/aspnet/core/security/authorization/introduction).</span><span class="sxs-lookup"><span data-stu-id="6c40f-126">For more information, see [Role-based authorization in ASP.NET Core](/aspnet/core/security/authorization/roles) and [Introduction to authorization in ASP.NET Core](/aspnet/core/security/authorization/introduction).</span></span>

- <span data-ttu-id="6c40f-127">**Si va a aplicar el atributo a código de biblioteca fuera del contexto de una aplicación web:**</span><span class="sxs-lookup"><span data-stu-id="6c40f-127">**If you're applying the attribute to library code outside the context of a web app:**</span></span>

  <span data-ttu-id="6c40f-128">Realice las comprobaciones manualmente al principio del método.</span><span class="sxs-lookup"><span data-stu-id="6c40f-128">Perform the checks manually at the beginning of your method.</span></span> <span data-ttu-id="6c40f-129">Esto se puede hacer con el método <xref:System.Security.Principal.IPrincipal.IsInRole(System.String)?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6c40f-129">This can be done by using the <xref:System.Security.Principal.IPrincipal.IsInRole(System.String)?displayProperty=nameWithType> method.</span></span>

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

## <a name="affected-apis"></a><span data-ttu-id="6c40f-130">API afectadas</span><span class="sxs-lookup"><span data-stu-id="6c40f-130">Affected APIs</span></span>

- <xref:System.Security.Permissions.PrincipalPermissionAttribute?displayProperty=fullName>

<!--

#### Category

- Core .NET libraries
- Security

### Affected APIs

- `T:System.Security.Permissions.PrincipalPermissionAttribute`

-->
