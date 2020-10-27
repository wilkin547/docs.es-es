---
ms.openlocfilehash: d9526055041f036958699aa935aa6cfef494b520
ms.sourcegitcommit: 98d20cb038669dca4a195eb39af37d22ea9d008e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2020
ms.locfileid: "92434938"
---
### <a name="principalpermissionattribute-is-obsolete-as-error"></a><span data-ttu-id="0721f-101">PrincipalPermissionAttribute está obsoleto como error</span><span class="sxs-lookup"><span data-stu-id="0721f-101">PrincipalPermissionAttribute is obsolete as error</span></span>

<span data-ttu-id="0721f-102">El constructor <xref:System.Security.Permissions.PrincipalPermissionAttribute> está obsoleto y genera un error en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="0721f-102">The <xref:System.Security.Permissions.PrincipalPermissionAttribute> constructor is obsolete and produces a compile-time error.</span></span> <span data-ttu-id="0721f-103">No se puede crear una instancia de este atributo ni aplicarlo a un método.</span><span class="sxs-lookup"><span data-stu-id="0721f-103">You cannot instantiate this attribute or apply it to a method.</span></span>

#### <a name="change-description"></a><span data-ttu-id="0721f-104">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="0721f-104">Change description</span></span>

<span data-ttu-id="0721f-105">En .NET Framework y .NET Core, puede anotar métodos con el atributo <xref:System.Security.Permissions.PrincipalPermissionAttribute>.</span><span class="sxs-lookup"><span data-stu-id="0721f-105">On .NET Framework and .NET Core, you can annotate methods with the <xref:System.Security.Permissions.PrincipalPermissionAttribute> attribute.</span></span> <span data-ttu-id="0721f-106">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0721f-106">For example:</span></span>

```csharp
[PrincipalPermission(SecurityAction.Demand, Role = "Administrators")]
public void MyMethod()
{
    // Code that should only run when the current user is an administrator.
}
```

<span data-ttu-id="0721f-107">A partir de .NET 5.0, no se puede aplicar el atributo <xref:System.Security.Permissions.PrincipalPermissionAttribute> a un método.</span><span class="sxs-lookup"><span data-stu-id="0721f-107">Starting in .NET 5.0, you cannot apply the <xref:System.Security.Permissions.PrincipalPermissionAttribute> attribute to a method.</span></span> <span data-ttu-id="0721f-108">El constructor del atributo está obsoleto y genera un error en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="0721f-108">The constructor for the attribute is obsolete and produces a compile-time error.</span></span> <span data-ttu-id="0721f-109">A diferencia de otras advertencias de obsolescencia, el error no se puede suprimir.</span><span class="sxs-lookup"><span data-stu-id="0721f-109">Unlike other obsoletion warnings, you can't suppress the error.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="0721f-110">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="0721f-110">Reason for change</span></span>

<span data-ttu-id="0721f-111">El tipo <xref:System.Security.Permissions.PrincipalPermissionAttribute>, como otros tipos que colocan <xref:System.Security.Permissions.SecurityAttribute> como subclase, forma parte de la infraestructura de seguridad de acceso del código (CAS) de .NET.</span><span class="sxs-lookup"><span data-stu-id="0721f-111">The <xref:System.Security.Permissions.PrincipalPermissionAttribute> type, like other types that subclass <xref:System.Security.Permissions.SecurityAttribute>, is part of .NET's Code Access Security (CAS) infrastructure.</span></span> <span data-ttu-id="0721f-112">En .NET Framework 2.x-4.x, el entorno de ejecución aplica anotaciones <xref:System.Security.Permissions.PrincipalPermissionAttribute> a la entrada de método, incluso si la aplicación se ejecuta en un escenario de plena confianza.</span><span class="sxs-lookup"><span data-stu-id="0721f-112">In .NET Framework 2.x - 4.x, the runtime enforces <xref:System.Security.Permissions.PrincipalPermissionAttribute> annotations on method entry, even if the application is running under a full-trust scenario.</span></span> <span data-ttu-id="0721f-113">.NET Core y .NET 5.0 y posterior no admiten atributos CAS y el entorno de ejecución los omite.</span><span class="sxs-lookup"><span data-stu-id="0721f-113">.NET Core and .NET 5.0 and later don't support CAS attributes, and the runtime ignores them.</span></span>

<span data-ttu-id="0721f-114">Esta diferencia de comportamiento entre .NET Framework y .NET Core y .NET 5.0 puede dar lugar a un escenario de "error de apertura", en el que se debería haber bloqueado el acceso pero, por el contrario, se ha permitido.</span><span class="sxs-lookup"><span data-stu-id="0721f-114">This difference in behavior from .NET Framework to .NET Core and .NET 5.0 can result in a "fail open" scenario, where access should have been blocked but instead has been allowed.</span></span> <span data-ttu-id="0721f-115">Para evitar el escenario de "error de apertura", ya no se puede aplicar el atributo en el código que tiene como destino .NET 5.0 o posterior.</span><span class="sxs-lookup"><span data-stu-id="0721f-115">To prevent the "fail open" scenario, you can no longer apply the attribute in code that targets .NET 5.0 or later.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="0721f-116">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="0721f-116">Version introduced</span></span>

<span data-ttu-id="0721f-117">5.0 (versión preliminar 7)</span><span class="sxs-lookup"><span data-stu-id="0721f-117">5.0 Preview 7</span></span>

#### <a name=""></a><span data-ttu-id="0721f-118"><a id="permission-action">Acción recomendada</a></span><span class="sxs-lookup"><span data-stu-id="0721f-118"><a id="permission-action">Recommended action</a></span></span>

<span data-ttu-id="0721f-119">Si se produce el error de obsolescencia, debe tomar medidas.</span><span class="sxs-lookup"><span data-stu-id="0721f-119">If you encounter the obsoletion error, you must take action.</span></span>

- <span data-ttu-id="0721f-120">**Si va a aplicar el atributo a un método de acción de MVC de ASP.NET:**</span><span class="sxs-lookup"><span data-stu-id="0721f-120">**If you're applying the attribute to an ASP.NET MVC action method:**</span></span>

  <span data-ttu-id="0721f-121">Considere la posibilidad de usar la infraestructura de autorización integrada de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="0721f-121">Consider using ASP.NET's built-in authorization infrastructure.</span></span> <span data-ttu-id="0721f-122">En el código siguiente se muestra cómo anotar un controlador con un atributo <xref:System.Web.Mvc.AuthorizeAttribute>.</span><span class="sxs-lookup"><span data-stu-id="0721f-122">The following code demonstrates how to annotate a controller with an <xref:System.Web.Mvc.AuthorizeAttribute> attribute.</span></span> <span data-ttu-id="0721f-123">El entorno de ejecución de ASP.NET autoriza al usuario antes de realizar la acción.</span><span class="sxs-lookup"><span data-stu-id="0721f-123">The ASP.NET runtime will authorize the user before performing the action.</span></span>

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

  <span data-ttu-id="0721f-124">Para obtener más información, vea [Autorización basada en roles en ASP.NET Core](/aspnet/core/security/authorization/roles) e [Introducción a la autorización en ASP.NET Core](/aspnet/core/security/authorization/introduction).</span><span class="sxs-lookup"><span data-stu-id="0721f-124">For more information, see [Role-based authorization in ASP.NET Core](/aspnet/core/security/authorization/roles) and [Introduction to authorization in ASP.NET Core](/aspnet/core/security/authorization/introduction).</span></span>

- <span data-ttu-id="0721f-125">**Si va a aplicar el atributo a código de biblioteca fuera del contexto de una aplicación web:**</span><span class="sxs-lookup"><span data-stu-id="0721f-125">**If you're applying the attribute to library code outside the context of a web app:**</span></span>

  <span data-ttu-id="0721f-126">Realice las comprobaciones manualmente al principio del método.</span><span class="sxs-lookup"><span data-stu-id="0721f-126">Perform the checks manually at the beginning of your method.</span></span> <span data-ttu-id="0721f-127">Esto se puede hacer con el método <xref:System.Security.Principal.IPrincipal.IsInRole(System.String)?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0721f-127">This can be done by using the <xref:System.Security.Principal.IPrincipal.IsInRole(System.String)?displayProperty=nameWithType> method.</span></span>

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

#### <a name="category"></a><span data-ttu-id="0721f-128">Categoría</span><span class="sxs-lookup"><span data-stu-id="0721f-128">Category</span></span>

- <span data-ttu-id="0721f-129">Bibliotecas de Core .NET</span><span class="sxs-lookup"><span data-stu-id="0721f-129">Core .NET libraries</span></span>
- <span data-ttu-id="0721f-130">Seguridad</span><span class="sxs-lookup"><span data-stu-id="0721f-130">Security</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="0721f-131">API afectadas</span><span class="sxs-lookup"><span data-stu-id="0721f-131">Affected APIs</span></span>

- <xref:System.Security.Permissions.PrincipalPermissionAttribute?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Security.Permissions.PrincipalPermissionAttribute`

-->
