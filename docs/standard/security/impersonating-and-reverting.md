---
description: Más información acerca de cómo suplantar y revertir
title: Suplantar y revertir
ms.date: 07/15/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WindowsIdentity objects, impersonating
- security [.NET], impersonating Windows accounts
- impersonating Windows accounts
ms.assetid: b93d402c-6c28-4f50-b2bc-d9607dc3e470
ms.openlocfilehash: f3e536f87ef5aa09cd727fe9674c7a40f3a09150
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99685015"
---
# <a name="impersonating-and-reverting"></a><span data-ttu-id="1af68-103">Suplantar y revertir</span><span class="sxs-lookup"><span data-stu-id="1af68-103">Impersonating and Reverting</span></span>

> [!NOTE]
> <span data-ttu-id="1af68-104">Este artículo se aplica a Windows.</span><span class="sxs-lookup"><span data-stu-id="1af68-104">This article applies to Windows.</span></span>
>
> <span data-ttu-id="1af68-105">Para obtener información sobre ASP.NET Core, consulte [ASP.net Core Security](/aspnet/core/security/).</span><span class="sxs-lookup"><span data-stu-id="1af68-105">For information about ASP.NET Core, see [ASP.NET Core Security](/aspnet/core/security/).</span></span>

<span data-ttu-id="1af68-106">En ocasiones es posible que deba obtener un token de cuenta de Windows para suplantar una cuenta de Windows.</span><span class="sxs-lookup"><span data-stu-id="1af68-106">Sometimes you might need to obtain a Windows account token to impersonate a Windows account.</span></span> <span data-ttu-id="1af68-107">Por ejemplo, la aplicación basada en ASP.NET podría tener que actuar en nombre de varios usuarios en momentos distintos.</span><span class="sxs-lookup"><span data-stu-id="1af68-107">For example, your ASP.NET-based application might have to act on behalf of several users at different times.</span></span> <span data-ttu-id="1af68-108">La aplicación podría aceptar un token que represente un administrador de Internet Information Services (IIS), suplantar al usuario, realizar una operación y revertir a la identidad anterior.</span><span class="sxs-lookup"><span data-stu-id="1af68-108">Your application might accept a token that represents an administrator from Internet Information Services (IIS), impersonate that user, perform an operation, and revert to the previous identity.</span></span> <span data-ttu-id="1af68-109">A continuación, podría aceptar un token de IIS que represente a un usuario con menos derechos, realizar alguna operación y revertir de nuevo.</span><span class="sxs-lookup"><span data-stu-id="1af68-109">Next, it might accept a token from IIS that represents a user with fewer rights, perform some operation, and revert again.</span></span>  
  
 <span data-ttu-id="1af68-110">En situaciones donde la aplicación deba suplantar una cuenta de Windows que IIS no haya asociado al subproceso actual, debe recuperar el token de esa cuenta y usarlo para activar la cuenta.</span><span class="sxs-lookup"><span data-stu-id="1af68-110">In situations where your application must impersonate a Windows account that has not been attached to the current thread by IIS, you must retrieve that account's token and use it to activate the account.</span></span> <span data-ttu-id="1af68-111">Para ello, debe realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="1af68-111">You can do this by performing the following tasks:</span></span>  
  
1. <span data-ttu-id="1af68-112">Recupere un token de cuenta de un usuario concreto haciendo una llamada al método **LogonUser** no administrado.</span><span class="sxs-lookup"><span data-stu-id="1af68-112">Retrieve an account token for a particular user by making a call to the unmanaged **LogonUser** method.</span></span> <span data-ttu-id="1af68-113">Este método no está en la biblioteca de clases base de .NET, sino que se encuentra en la **advapi32.dll** no administrada.</span><span class="sxs-lookup"><span data-stu-id="1af68-113">This method is not in the .NET base class library, but is located in the unmanaged **advapi32.dll**.</span></span> <span data-ttu-id="1af68-114">El acceso a métodos en código no administrado es una operación avanzada y queda fuera del ámbito de este contenido.</span><span class="sxs-lookup"><span data-stu-id="1af68-114">Accessing methods in unmanaged code is an advanced operation and is beyond the scope of this discussion.</span></span> <span data-ttu-id="1af68-115">Para más información, consulte [Interoperating with Unmanaged Code](../../framework/interop/index.md) (Interoperar con código no administrado)</span><span class="sxs-lookup"><span data-stu-id="1af68-115">For more information, see [Interoperating with Unmanaged Code](../../framework/interop/index.md).</span></span> <span data-ttu-id="1af68-116">Para más información sobre el método **LogonUser** y el archivo **advapi32.dll**, consulte la documentación de Platform SDK.</span><span class="sxs-lookup"><span data-stu-id="1af68-116">For more information about the **LogonUser** method and **advapi32.dll**, see the Platform SDK documentation.</span></span>  
  
2. <span data-ttu-id="1af68-117">Cree una nueva instancia de la clase **WindowsIdentity**, pasando el token.</span><span class="sxs-lookup"><span data-stu-id="1af68-117">Create a new instance of the **WindowsIdentity** class, passing the token.</span></span> <span data-ttu-id="1af68-118">En el siguiente código se muestra esta llamada, donde `hToken` representa un token de Windows.</span><span class="sxs-lookup"><span data-stu-id="1af68-118">The following code demonstrates this call, where `hToken` represents a Windows token.</span></span>  
  
    ```csharp  
    WindowsIdentity impersonatedIdentity = new WindowsIdentity(hToken);  
    ```  
  
    ```vb  
    Dim impersonatedIdentity As New WindowsIdentity(hToken)  
    ```  
  
3. <span data-ttu-id="1af68-119">Comience la suplantación con la creación de una nueva instancia de la clase <xref:System.Security.Principal.WindowsImpersonationContext> e inicialícela con el método <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A?displayProperty=nameWithType> de la clase inicializada, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="1af68-119">Begin impersonation by creating a new instance of the <xref:System.Security.Principal.WindowsImpersonationContext> class and initializing it with the <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A?displayProperty=nameWithType> method of the initialized class, as shown in the following code.</span></span>  
  
    ```csharp  
    WindowsImpersonationContext myImpersonation = impersonatedIdentity.Impersonate();  
    ```  
  
    ```vb  
    WindowsImpersonationContext myImpersonation = impersonatedIdentity.Impersonate()  
    ```  
  
4. <span data-ttu-id="1af68-120">Cuando ya no necesite suplantar, llame al método <xref:System.Security.Principal.WindowsImpersonationContext.Undo%2A?displayProperty=nameWithType> para revertir la suplantación, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="1af68-120">When you no longer need to impersonate, call the <xref:System.Security.Principal.WindowsImpersonationContext.Undo%2A?displayProperty=nameWithType> method to revert the impersonation, as shown in the following code.</span></span>  
  
    ```csharp  
    myImpersonation.Undo();  
    ```  
  
    ```vb  
    myImpersonation.Undo()  
    ```  
  
 <span data-ttu-id="1af68-121">Si el código de confianza ya ha asociado un <xref:System.Security.Principal.WindowsPrincipal> objeto al subproceso, puede llamar al método de instancia **Impersonate**, que no toma un token de cuenta.</span><span class="sxs-lookup"><span data-stu-id="1af68-121">If trusted code has already attached a <xref:System.Security.Principal.WindowsPrincipal> object to the thread, you can call the instance method **Impersonate**, which does not take an account token.</span></span> <span data-ttu-id="1af68-122">Tenga en cuenta que esto solo es útil cuando el objeto **WindowsPrincipal** del subproceso representa a un usuario que no es en el que se está ejecutando el proceso.</span><span class="sxs-lookup"><span data-stu-id="1af68-122">Note that this is only useful when the **WindowsPrincipal** object on the thread represents a user other than the one under which the process is currently executing.</span></span> <span data-ttu-id="1af68-123">Por ejemplo, podría encontrarse con esta situación si usa ASP.NET con la autenticación de Windows activada y la suplantación desactivada.</span><span class="sxs-lookup"><span data-stu-id="1af68-123">For example, you might encounter this situation using ASP.NET with Windows authentication turned on and impersonation turned off.</span></span> <span data-ttu-id="1af68-124">En este caso, el proceso se ejecuta en una cuenta configurada en Internet Information Services (IIS) mientras la entidad de seguridad actual representa al usuario de Windows que está accediendo a la página.</span><span class="sxs-lookup"><span data-stu-id="1af68-124">In this case, the process is running under an account configured in Internet Information Services (IIS) while the current principal represents the Windows user that is accessing the page.</span></span>  
  
 <span data-ttu-id="1af68-125">Tenga en cuenta que ni **Impersonate** ni **Undo** cambian el objeto **principal** ( <xref:System.Security.Principal.IPrincipal> ) asociado al contexto de llamada actual.</span><span class="sxs-lookup"><span data-stu-id="1af68-125">Note that neither **Impersonate** nor **Undo** changes the **Principal** object (<xref:System.Security.Principal.IPrincipal>)  associated with the current call context.</span></span> <span data-ttu-id="1af68-126">En su lugar, la suplantación y la reversión cambian el token asociado con el proceso actual del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="1af68-126">Rather, impersonation and reverting change the token associated with the current operating system process.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1af68-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="1af68-127">See also</span></span>

- <xref:System.Security.Principal.WindowsIdentity>
- <xref:System.Security.Principal.WindowsImpersonationContext>
- [<span data-ttu-id="1af68-128">Objetos Principal e Identity</span><span class="sxs-lookup"><span data-stu-id="1af68-128">Principal and Identity Objects</span></span>](principal-and-identity-objects.md)
- <span data-ttu-id="1af68-129">[Interoperating with Unmanaged Code](../../framework/interop/index.md) (Interoperar con código no administrado)</span><span class="sxs-lookup"><span data-stu-id="1af68-129">[Interoperating with Unmanaged Code](../../framework/interop/index.md)</span></span>
- [<span data-ttu-id="1af68-130">Seguridad de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="1af68-130">ASP.NET Core Security</span></span>](/aspnet/core/security/)
