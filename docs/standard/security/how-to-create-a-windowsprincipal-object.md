---
title: 'Cómo: Crear un objeto WindowsPrincipal'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WindowsPrincipal objects, creating
- security [.NET Framework], creating a WindowsPrincipal object
- security [.NET Framework], principals
- principal objects, creating
ms.assetid: 56eb10ca-e61d-4ed2-af7a-555fc4c25a25
ms.openlocfilehash: d409c0e9a2a6564e5fb16e4e2c72ab661ae2d5ce
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706167"
---
# <a name="how-to-create-a-windowsprincipal-object"></a><span data-ttu-id="78dd7-102">Cómo: Crear un objeto WindowsPrincipal</span><span class="sxs-lookup"><span data-stu-id="78dd7-102">How to: Create a WindowsPrincipal Object</span></span>
<span data-ttu-id="78dd7-103">Hay dos maneras de crear un objeto <xref:System.Security.Principal.WindowsPrincipal>, dependiendo de si el código debe realizar la validación basada en rol una sola vez o varias veces.</span><span class="sxs-lookup"><span data-stu-id="78dd7-103">There are two ways to create a <xref:System.Security.Principal.WindowsPrincipal> object, depending on whether code must repeatedly perform role-based validation or must perform it only once.</span></span>  
  
 <span data-ttu-id="78dd7-104">Si el código debe realizar la validación basada en rol varias veces, el primero de los procedimientos indicados a continuación produce menos sobrecarga.</span><span class="sxs-lookup"><span data-stu-id="78dd7-104">If code must repeatedly perform role-based validation, the first of the following procedures produces less overhead.</span></span> <span data-ttu-id="78dd7-105">Cuando solo hace falta llevar a cabo una vez validaciones basadas en rol, puede crear un objeto <xref:System.Security.Principal.WindowsPrincipal> usando el segundo de los procedimientos indicados a continuación.</span><span class="sxs-lookup"><span data-stu-id="78dd7-105">When code needs to make role-based validations only once, you can create a <xref:System.Security.Principal.WindowsPrincipal> object by using the second of the following procedures.</span></span>  
  
### <a name="to-create-a-windowsprincipal-object-for-repeated-validation"></a><span data-ttu-id="78dd7-106">Para crear un objeto WindowsPrincipal para validar varias veces</span><span class="sxs-lookup"><span data-stu-id="78dd7-106">To create a WindowsPrincipal object for repeated validation</span></span>  
  
1. <span data-ttu-id="78dd7-107">Llame al método <xref:System.AppDomain.SetPrincipalPolicy%2A> en el objeto <xref:System.AppDomain> que devuelve la propiedad <xref:System.AppDomain.CurrentDomain%2A?displayProperty=nameWithType> estática, pasando al método un valor de enumeración <xref:System.Security.Principal.PrincipalPolicy> que indica cuál debe ser la nueva directiva.</span><span class="sxs-lookup"><span data-stu-id="78dd7-107">Call the <xref:System.AppDomain.SetPrincipalPolicy%2A> method on the <xref:System.AppDomain> object that is returned by the static <xref:System.AppDomain.CurrentDomain%2A?displayProperty=nameWithType> property, passing the method a <xref:System.Security.Principal.PrincipalPolicy> enumeration value that indicates what the new policy should be.</span></span> <span data-ttu-id="78dd7-108">Los valores admitidos son <xref:System.Security.Principal.PrincipalPolicy.NoPrincipal>, <xref:System.Security.Principal.PrincipalPolicy.UnauthenticatedPrincipal> y <xref:System.Security.Principal.PrincipalPolicy.WindowsPrincipal>.</span><span class="sxs-lookup"><span data-stu-id="78dd7-108">Supported values are <xref:System.Security.Principal.PrincipalPolicy.NoPrincipal>, <xref:System.Security.Principal.PrincipalPolicy.UnauthenticatedPrincipal>, and <xref:System.Security.Principal.PrincipalPolicy.WindowsPrincipal>.</span></span> <span data-ttu-id="78dd7-109">El siguiente código muestra cómo llamar a este método.</span><span class="sxs-lookup"><span data-stu-id="78dd7-109">The following code demonstrates this method call.</span></span>  
  
    ```csharp  
    AppDomain.CurrentDomain.SetPrincipalPolicy(  
        PrincipalPolicy.WindowsPrincipal);  
    ```  
  
    ```vb  
    AppDomain.CurrentDomain.SetPrincipalPolicy( _  
        PrincipalPolicy.WindowsPrincipal)  
    ```  
  
2. <span data-ttu-id="78dd7-110">Una vez que se haya establecido la directiva, use la propiedad <xref:System.Threading.Thread.CurrentPrincipal%2A?displayProperty=nameWithType> estática para recuperar la entidad de seguridad que encapsula al usuario de Windows actual.</span><span class="sxs-lookup"><span data-stu-id="78dd7-110">With the policy set, use the static <xref:System.Threading.Thread.CurrentPrincipal%2A?displayProperty=nameWithType> property to retrieve the principal that encapsulates the current Windows user.</span></span> <span data-ttu-id="78dd7-111">Dado que el tipo de devolución de la propiedad es <xref:System.Security.Principal.IPrincipal>, debe convertir el resultado en un tipo <xref:System.Security.Principal.WindowsPrincipal>.</span><span class="sxs-lookup"><span data-stu-id="78dd7-111">Because the property return type is <xref:System.Security.Principal.IPrincipal>, you must cast the result to a <xref:System.Security.Principal.WindowsPrincipal> type.</span></span> <span data-ttu-id="78dd7-112">El siguiente código inicializa un nuevo objeto <xref:System.Security.Principal.WindowsPrincipal> en el valor de la entidad de seguridad asociada al subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="78dd7-112">The following code initializes a new <xref:System.Security.Principal.WindowsPrincipal> object to the value of the principal associated with the current thread.</span></span>  
  
    ```csharp  
    WindowsPrincipal myPrincipal =   
        (WindowsPrincipal) Thread.CurrentPrincipal;  
    ```  
  
    ```vb  
    Dim myPrincipal As WindowsPrincipal = _  
        CType(Thread.CurrentPrincipal, WindowsPrincipal)   
    ```  
  
3. <span data-ttu-id="78dd7-113">Una vez que se ha creado el objeto de entidad de seguridad, dispone de varios métodos para validarlo.</span><span class="sxs-lookup"><span data-stu-id="78dd7-113">When the principal object has been created, you can use one of several methods to validate it.</span></span>  
  
### <a name="to-create-a-windowsprincipal-object-for-a-single-validation"></a><span data-ttu-id="78dd7-114">Para crear un objeto WindowsPrincipal para validar una sola vez</span><span class="sxs-lookup"><span data-stu-id="78dd7-114">To create a WindowsPrincipal object for a single validation</span></span>  
  
1. <span data-ttu-id="78dd7-115">Inicialice un nuevo objeto <xref:System.Security.Principal.WindowsIdentity> llamando al método <xref:System.Security.Principal.WindowsIdentity.GetCurrent%2A?displayProperty=nameWithType> estático, que consulta la cuenta de Windows actual y coloca la información sobre esa cuenta en el objeto de identidad recién creado.</span><span class="sxs-lookup"><span data-stu-id="78dd7-115">Initialize a new <xref:System.Security.Principal.WindowsIdentity> object by calling the static <xref:System.Security.Principal.WindowsIdentity.GetCurrent%2A?displayProperty=nameWithType> method, which queries the current Windows account and places information about that account into the newly created identity object.</span></span> <span data-ttu-id="78dd7-116">El siguiente código crea un nuevo objeto <xref:System.Security.Principal.WindowsIdentity> y lo inicializa en el usuario autenticado actual.</span><span class="sxs-lookup"><span data-stu-id="78dd7-116">The following code creates a new <xref:System.Security.Principal.WindowsIdentity> object and initializes it to the current authenticated user.</span></span>  
  
    ```csharp  
    WindowsIdentity myIdentity = WindowsIdentity.GetCurrent();  
    ```  
  
    ```vb  
    Dim myIdentity As WindowsIdentity = WindowsIdentity.GetCurrent()  
    ```  
  
2. <span data-ttu-id="78dd7-117">Cree un nuevo objeto <xref:System.Security.Principal.WindowsPrincipal> y pásele el valor del objeto <xref:System.Security.Principal.WindowsIdentity> que se creó en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="78dd7-117">Create a new <xref:System.Security.Principal.WindowsPrincipal> object and pass it the value of the <xref:System.Security.Principal.WindowsIdentity> object created in the preceding step.</span></span>  
  
    ```csharp  
    WindowsPrincipal myPrincipal = new WindowsPrincipal(myIdentity);  
    ```  
  
    ```vb  
    Dim myPrincipal As New WindowsPrincipal(myIdentity)  
    ```  
  
3. <span data-ttu-id="78dd7-118">Una vez que se ha creado el objeto de entidad de seguridad, dispone de varios métodos para validarlo.</span><span class="sxs-lookup"><span data-stu-id="78dd7-118">When the principal object has been created, you can use one of several methods to validate it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78dd7-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="78dd7-119">See also</span></span>

- [<span data-ttu-id="78dd7-120">Objetos Principal e Identity</span><span class="sxs-lookup"><span data-stu-id="78dd7-120">Principal and Identity Objects</span></span>](../../../docs/standard/security/principal-and-identity-objects.md)
