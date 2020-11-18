---
title: Procedimiento para crear un objeto WindowsPrincipal
ms.date: 07/15/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WindowsPrincipal objects, creating
- security [.NET], creating a WindowsPrincipal object
- security [.NET], principals
- principal objects, creating
ms.assetid: 56eb10ca-e61d-4ed2-af7a-555fc4c25a25
ms.openlocfilehash: d4140470308a09774e5e4eee429c1e91b559d063
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94819037"
---
# <a name="how-to-create-a-windowsprincipal-object"></a><span data-ttu-id="3e784-102">Procedimiento para crear un objeto WindowsPrincipal</span><span class="sxs-lookup"><span data-stu-id="3e784-102">How to: Create a WindowsPrincipal Object</span></span>

> [!NOTE]
> <span data-ttu-id="3e784-103">Este artículo se aplica a Windows.</span><span class="sxs-lookup"><span data-stu-id="3e784-103">This article applies to Windows.</span></span>
>
> <span data-ttu-id="3e784-104">Para obtener información sobre ASP.NET Core, consulte [ASP.net Core Security](/aspnet/core/security/).</span><span class="sxs-lookup"><span data-stu-id="3e784-104">For information about ASP.NET Core, see [ASP.NET Core Security](/aspnet/core/security/).</span></span>

<span data-ttu-id="3e784-105">Hay dos maneras de crear un objeto <xref:System.Security.Principal.WindowsPrincipal>, dependiendo de si el código debe realizar la validación basada en rol una sola vez o varias veces.</span><span class="sxs-lookup"><span data-stu-id="3e784-105">There are two ways to create a <xref:System.Security.Principal.WindowsPrincipal> object, depending on whether code must repeatedly perform role-based validation or must perform it only once.</span></span>  
  
<span data-ttu-id="3e784-106">Si el código debe realizar la validación basada en rol varias veces, el primero de los procedimientos indicados a continuación produce menos sobrecarga.</span><span class="sxs-lookup"><span data-stu-id="3e784-106">If code must repeatedly perform role-based validation, the first of the following procedures produces less overhead.</span></span> <span data-ttu-id="3e784-107">Cuando solo hace falta llevar a cabo una vez validaciones basadas en rol, puede crear un objeto <xref:System.Security.Principal.WindowsPrincipal> usando el segundo de los procedimientos indicados a continuación.</span><span class="sxs-lookup"><span data-stu-id="3e784-107">When code needs to make role-based validations only once, you can create a <xref:System.Security.Principal.WindowsPrincipal> object by using the second of the following procedures.</span></span>  
  
### <a name="to-create-a-windowsprincipal-object-for-repeated-validation"></a><span data-ttu-id="3e784-108">Para crear un objeto WindowsPrincipal para validar varias veces</span><span class="sxs-lookup"><span data-stu-id="3e784-108">To create a WindowsPrincipal object for repeated validation</span></span>  
  
1. <span data-ttu-id="3e784-109">Llame al método <xref:System.AppDomain.SetPrincipalPolicy%2A> en el objeto <xref:System.AppDomain> que devuelve la propiedad <xref:System.AppDomain.CurrentDomain%2A?displayProperty=nameWithType> estática, pasando al método un valor de enumeración <xref:System.Security.Principal.PrincipalPolicy> que indica cuál debe ser la nueva directiva.</span><span class="sxs-lookup"><span data-stu-id="3e784-109">Call the <xref:System.AppDomain.SetPrincipalPolicy%2A> method on the <xref:System.AppDomain> object that is returned by the static <xref:System.AppDomain.CurrentDomain%2A?displayProperty=nameWithType> property, passing the method a <xref:System.Security.Principal.PrincipalPolicy> enumeration value that indicates what the new policy should be.</span></span> <span data-ttu-id="3e784-110">Los valores admitidos son <xref:System.Security.Principal.PrincipalPolicy.NoPrincipal>, <xref:System.Security.Principal.PrincipalPolicy.UnauthenticatedPrincipal> y <xref:System.Security.Principal.PrincipalPolicy.WindowsPrincipal>.</span><span class="sxs-lookup"><span data-stu-id="3e784-110">Supported values are <xref:System.Security.Principal.PrincipalPolicy.NoPrincipal>, <xref:System.Security.Principal.PrincipalPolicy.UnauthenticatedPrincipal>, and <xref:System.Security.Principal.PrincipalPolicy.WindowsPrincipal>.</span></span> <span data-ttu-id="3e784-111">El siguiente código muestra cómo llamar a este método.</span><span class="sxs-lookup"><span data-stu-id="3e784-111">The following code demonstrates this method call.</span></span>  
  
    ```csharp  
    AppDomain.CurrentDomain.SetPrincipalPolicy(  
        PrincipalPolicy.WindowsPrincipal);  
    ```  
  
    ```vb  
    AppDomain.CurrentDomain.SetPrincipalPolicy( _  
        PrincipalPolicy.WindowsPrincipal)  
    ```  
  
2. <span data-ttu-id="3e784-112">Una vez que se haya establecido la directiva, use la propiedad <xref:System.Threading.Thread.CurrentPrincipal%2A?displayProperty=nameWithType> estática para recuperar la entidad de seguridad que encapsula al usuario de Windows actual.</span><span class="sxs-lookup"><span data-stu-id="3e784-112">With the policy set, use the static <xref:System.Threading.Thread.CurrentPrincipal%2A?displayProperty=nameWithType> property to retrieve the principal that encapsulates the current Windows user.</span></span> <span data-ttu-id="3e784-113">Dado que el tipo de devolución de la propiedad es <xref:System.Security.Principal.IPrincipal>, debe convertir el resultado en un tipo <xref:System.Security.Principal.WindowsPrincipal>.</span><span class="sxs-lookup"><span data-stu-id="3e784-113">Because the property return type is <xref:System.Security.Principal.IPrincipal>, you must cast the result to a <xref:System.Security.Principal.WindowsPrincipal> type.</span></span> <span data-ttu-id="3e784-114">El siguiente código inicializa un nuevo objeto <xref:System.Security.Principal.WindowsPrincipal> en el valor de la entidad de seguridad asociada al subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="3e784-114">The following code initializes a new <xref:System.Security.Principal.WindowsPrincipal> object to the value of the principal associated with the current thread.</span></span>  
  
    ```csharp  
    WindowsPrincipal myPrincipal =
        (WindowsPrincipal) Thread.CurrentPrincipal;  
    ```  
  
    ```vb  
    Dim myPrincipal As WindowsPrincipal = _  
        CType(Thread.CurrentPrincipal, WindowsPrincipal)
    ```  
  
3. <span data-ttu-id="3e784-115">Una vez que se ha creado el objeto de entidad de seguridad, dispone de varios métodos para validarlo.</span><span class="sxs-lookup"><span data-stu-id="3e784-115">When the principal object has been created, you can use one of several methods to validate it.</span></span>  
  
### <a name="to-create-a-windowsprincipal-object-for-a-single-validation"></a><span data-ttu-id="3e784-116">Para crear un objeto WindowsPrincipal para validar una sola vez</span><span class="sxs-lookup"><span data-stu-id="3e784-116">To create a WindowsPrincipal object for a single validation</span></span>  
  
1. <span data-ttu-id="3e784-117">Inicialice un nuevo objeto <xref:System.Security.Principal.WindowsIdentity> llamando al método <xref:System.Security.Principal.WindowsIdentity.GetCurrent%2A?displayProperty=nameWithType> estático, que consulta la cuenta de Windows actual y coloca la información sobre esa cuenta en el objeto de identidad recién creado.</span><span class="sxs-lookup"><span data-stu-id="3e784-117">Initialize a new <xref:System.Security.Principal.WindowsIdentity> object by calling the static <xref:System.Security.Principal.WindowsIdentity.GetCurrent%2A?displayProperty=nameWithType> method, which queries the current Windows account and places information about that account into the newly created identity object.</span></span> <span data-ttu-id="3e784-118">El siguiente código crea un nuevo objeto <xref:System.Security.Principal.WindowsIdentity> y lo inicializa en el usuario autenticado actual.</span><span class="sxs-lookup"><span data-stu-id="3e784-118">The following code creates a new <xref:System.Security.Principal.WindowsIdentity> object and initializes it to the current authenticated user.</span></span>  
  
    ```csharp  
    WindowsIdentity myIdentity = WindowsIdentity.GetCurrent();  
    ```  
  
    ```vb  
    Dim myIdentity As WindowsIdentity = WindowsIdentity.GetCurrent()  
    ```  
  
2. <span data-ttu-id="3e784-119">Cree un nuevo objeto <xref:System.Security.Principal.WindowsPrincipal> y pásele el valor del objeto <xref:System.Security.Principal.WindowsIdentity> que se creó en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="3e784-119">Create a new <xref:System.Security.Principal.WindowsPrincipal> object and pass it the value of the <xref:System.Security.Principal.WindowsIdentity> object created in the preceding step.</span></span>  
  
    ```csharp  
    WindowsPrincipal myPrincipal = new WindowsPrincipal(myIdentity);  
    ```  
  
    ```vb  
    Dim myPrincipal As New WindowsPrincipal(myIdentity)  
    ```  
  
3. <span data-ttu-id="3e784-120">Una vez que se ha creado el objeto de entidad de seguridad, dispone de varios métodos para validarlo.</span><span class="sxs-lookup"><span data-stu-id="3e784-120">When the principal object has been created, you can use one of several methods to validate it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e784-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="3e784-121">See also</span></span>

- [<span data-ttu-id="3e784-122">Objetos Principal e Identity</span><span class="sxs-lookup"><span data-stu-id="3e784-122">Principal and Identity Objects</span></span>](principal-and-identity-objects.md)
- [<span data-ttu-id="3e784-123">Seguridad de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="3e784-123">ASP.NET Core Security</span></span>](/aspnet/core/security/)
