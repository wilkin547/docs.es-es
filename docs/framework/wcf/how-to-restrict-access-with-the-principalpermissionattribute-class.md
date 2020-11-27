---
title: Procedimiento para restringir el acceso con la clase PrincipalPermissionAttribute
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PrincipalPermissionAttribute class
- WCF, authorization
- WCF, security
ms.assetid: 5162f5c4-8781-4cc4-9425-bb7620eaeaf4
ms.openlocfilehash: 92d27548c510a19bf36ffaffb532f48461146d99
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96269618"
---
# <a name="how-to-restrict-access-with-the-principalpermissionattribute-class"></a><span data-ttu-id="39a73-102">Procedimiento para restringir el acceso con la clase PrincipalPermissionAttribute</span><span class="sxs-lookup"><span data-stu-id="39a73-102">How to: Restrict Access with the PrincipalPermissionAttribute Class</span></span>

<span data-ttu-id="39a73-103">Controlar el acceso a los recursos en un equipo del dominio de Windows es una tarea de seguridad básica.</span><span class="sxs-lookup"><span data-stu-id="39a73-103">Controlling the access to resources on a Windows-domain computer is a basic security task.</span></span> <span data-ttu-id="39a73-104">Por ejemplo, solo ciertos usuarios deberían poder ver los datos confidenciales, como la información de la nómina.</span><span class="sxs-lookup"><span data-stu-id="39a73-104">For example, only certain users should be able to view sensitive data, such as payroll information.</span></span> <span data-ttu-id="39a73-105">Este tema explica cómo restringir el acceso a un método exigiendo que el usuario pertenezca a un grupo predefinido.</span><span class="sxs-lookup"><span data-stu-id="39a73-105">This topic explains how to restrict access to a method by demanding that the user belong to a predefined group.</span></span> <span data-ttu-id="39a73-106">Para obtener un ejemplo de trabajo, vea el apartado sobre cómo [autorizar el acceso a las operaciones de servicio](./samples/authorizing-access-to-service-operations.md).</span><span class="sxs-lookup"><span data-stu-id="39a73-106">For a working sample, see [Authorizing Access to Service Operations](./samples/authorizing-access-to-service-operations.md).</span></span>  
  
 <span data-ttu-id="39a73-107">La tarea está compuesta de dos procedimientos independientes.</span><span class="sxs-lookup"><span data-stu-id="39a73-107">The task consists of two separate procedures.</span></span> <span data-ttu-id="39a73-108">El primero crea el grupo y lo rellena con usuarios.</span><span class="sxs-lookup"><span data-stu-id="39a73-108">The first creates the group and populates it with users.</span></span> <span data-ttu-id="39a73-109">El segundo aplica la clase <xref:System.Security.Permissions.PrincipalPermissionAttribute> para especificar el grupo.</span><span class="sxs-lookup"><span data-stu-id="39a73-109">The second applies the <xref:System.Security.Permissions.PrincipalPermissionAttribute> class to specify the group.</span></span>  
  
### <a name="to-create-a-windows-group"></a><span data-ttu-id="39a73-110">Para crear un grupo de Windows</span><span class="sxs-lookup"><span data-stu-id="39a73-110">To create a Windows group</span></span>  
  
1. <span data-ttu-id="39a73-111">Abra la consola de **Administración de equipos** .</span><span class="sxs-lookup"><span data-stu-id="39a73-111">Open the **Computer Management** console.</span></span>  
  
2. <span data-ttu-id="39a73-112">En el panel izquierdo, haga clic en **usuarios y grupos locales**.</span><span class="sxs-lookup"><span data-stu-id="39a73-112">In the left panel, click **Local Users and Groups**.</span></span>  
  
3. <span data-ttu-id="39a73-113">Haga clic con el botón secundario en **grupos** y haga clic en **nuevo grupo**.</span><span class="sxs-lookup"><span data-stu-id="39a73-113">Right-click **Groups**, and click **New Group**.</span></span>  
  
4. <span data-ttu-id="39a73-114">En el cuadro **nombre de grupo** , escriba un nombre para el nuevo grupo.</span><span class="sxs-lookup"><span data-stu-id="39a73-114">In the **Group Name** box, type a name for the new group.</span></span>  
  
5. <span data-ttu-id="39a73-115">En el cuadro **Descripción** , escriba una descripción del nuevo grupo.</span><span class="sxs-lookup"><span data-stu-id="39a73-115">In the **Description** box, type a description of the new group.</span></span>  
  
6. <span data-ttu-id="39a73-116">Haga clic en el botón **Agregar** para agregar nuevos miembros al grupo.</span><span class="sxs-lookup"><span data-stu-id="39a73-116">Click the **Add** button to add new members to the group.</span></span>  
  
7. <span data-ttu-id="39a73-117">Si se ha agregado al grupo y desea probar el código siguiente, debe cerrar la sesión en el equipo y volver a iniciarla para estar incluido en el grupo.</span><span class="sxs-lookup"><span data-stu-id="39a73-117">If you have added yourself to the group and want to test the following code, you must log off the computer and log back on to be included in the group.</span></span>  
  
### <a name="to-demand-user-membership"></a><span data-ttu-id="39a73-118">Para exigir la pertenencia del usuario</span><span class="sxs-lookup"><span data-stu-id="39a73-118">To demand user membership</span></span>  
  
1. <span data-ttu-id="39a73-119">Abra el archivo de código Windows Communication Foundation (WCF) que contiene el código de contrato de servicio implementado.</span><span class="sxs-lookup"><span data-stu-id="39a73-119">Open the Windows Communication Foundation (WCF) code file that contains the implemented service contract code.</span></span> <span data-ttu-id="39a73-120">Para obtener más información sobre la implementación de un contrato, consulte [implementación de contratos de servicio](implementing-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="39a73-120">For more information about implementing a contract, see [Implementing Service Contracts](implementing-service-contracts.md).</span></span>  
  
2. <span data-ttu-id="39a73-121">Aplique el atributo <xref:System.Security.Permissions.PrincipalPermissionAttribute> a cada método que debe estar restringido a un grupo concreto.</span><span class="sxs-lookup"><span data-stu-id="39a73-121">Apply the <xref:System.Security.Permissions.PrincipalPermissionAttribute> attribute to each method that must be restricted to a specific group.</span></span> <span data-ttu-id="39a73-122">Establezca la propiedad <xref:System.Security.Permissions.SecurityAttribute.Action%2A> en <xref:System.Security.Permissions.SecurityAction.Demand> y la propiedad <xref:System.Security.Permissions.PrincipalPermissionAttribute.Role%2A> en el nombre del grupo.</span><span class="sxs-lookup"><span data-stu-id="39a73-122">Set the <xref:System.Security.Permissions.SecurityAttribute.Action%2A> property to <xref:System.Security.Permissions.SecurityAction.Demand> and the <xref:System.Security.Permissions.PrincipalPermissionAttribute.Role%2A> property to the name of the group.</span></span> <span data-ttu-id="39a73-123">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="39a73-123">For example:</span></span>  
  
     [!code-csharp[c_PrincipalPermissionAttribute#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_principalpermissionattribute/cs/source.cs#1)]
     [!code-vb[c_PrincipalPermissionAttribute#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_principalpermissionattribute/vb/source.vb#1)]  
  
    > [!NOTE]
    > <span data-ttu-id="39a73-124">Si se aplica el atributo a un contrato <xref:System.Security.Permissions.PrincipalPermissionAttribute>, se iniciará una <xref:System.Security.SecurityException>.</span><span class="sxs-lookup"><span data-stu-id="39a73-124">If you apply the <xref:System.Security.Permissions.PrincipalPermissionAttribute> attribute to a contract a <xref:System.Security.SecurityException> will be thrown.</span></span> <span data-ttu-id="39a73-125">El atributo solo puede aplicarse en el nivel del método.</span><span class="sxs-lookup"><span data-stu-id="39a73-125">You can only apply the attribute at the method level.</span></span>  
  
## <a name="using-a-certificate-to-control-access-to-a-method"></a><span data-ttu-id="39a73-126">Uso de un certificado para controlar el acceso a un método</span><span class="sxs-lookup"><span data-stu-id="39a73-126">Using a Certificate to Control Access to a Method</span></span>  

 <span data-ttu-id="39a73-127">También puede utilizar la clase `PrincipalPermissionAttribute` para controlar el acceso a un método si el tipo de credencial de cliente es un certificado.</span><span class="sxs-lookup"><span data-stu-id="39a73-127">You can also use the `PrincipalPermissionAttribute` class to control access to a method if the client credential type is a certificate.</span></span> <span data-ttu-id="39a73-128">Para hacerlo, debe tener el asunto y la huella digital del certificado.</span><span class="sxs-lookup"><span data-stu-id="39a73-128">To do this, you must have the certificate's subject and thumbprint.</span></span>  
  
 <span data-ttu-id="39a73-129">Para examinar un certificado para sus propiedades, consulte [Cómo: ver certificados con el complemento MMC](./feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).</span><span class="sxs-lookup"><span data-stu-id="39a73-129">To examine a certificate for its properties, see [How to: View Certificates with the MMC Snap-in](./feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).</span></span> <span data-ttu-id="39a73-130">Para buscar el valor de huella digital, consulte [Cómo: recuperar la huella digital de un certificado](./feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).</span><span class="sxs-lookup"><span data-stu-id="39a73-130">To find the thumbprint value, see [How to: Retrieve the Thumbprint of a Certificate](./feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).</span></span>  
  
#### <a name="to-control-access-using-a-certificate"></a><span data-ttu-id="39a73-131">Para controlar el acceso mediante un certificado</span><span class="sxs-lookup"><span data-stu-id="39a73-131">To control access using a certificate</span></span>  
  
1. <span data-ttu-id="39a73-132">Aplique la clase <xref:System.Security.Permissions.PrincipalPermissionAttribute> al método al que desea restringir el acceso.</span><span class="sxs-lookup"><span data-stu-id="39a73-132">Apply the <xref:System.Security.Permissions.PrincipalPermissionAttribute> class to the method you want to restrict access to.</span></span>  
  
2. <span data-ttu-id="39a73-133">Establezca la acción del atributo en <xref:System.Security.Permissions.SecurityAction.Demand?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="39a73-133">Set the action of the attribute to <xref:System.Security.Permissions.SecurityAction.Demand?displayProperty=nameWithType>.</span></span>  
  
3. <span data-ttu-id="39a73-134">Establezca la propiedad `Name` en una cadena que esté compuesta del nombre del sujeto y la huella digital del certificado.</span><span class="sxs-lookup"><span data-stu-id="39a73-134">Set the `Name` property to a string that consists of the subject name and the certificate's thumbprint.</span></span> <span data-ttu-id="39a73-135">Separe los dos valores con un punto y coma y un espacio, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="39a73-135">Separate the two values with a semicolon and a space, as shown in the following example:</span></span>  
  
     [!code-csharp[c_PrincipalPermissionAttribute#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_principalpermissionattribute/cs/source.cs#2)]
     [!code-vb[c_PrincipalPermissionAttribute#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_principalpermissionattribute/vb/source.vb#2)]  
  
4. <span data-ttu-id="39a73-136">Establezca la propiedad <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> en <xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles> como se muestra en el siguiente ejemplo de configuración:</span><span class="sxs-lookup"><span data-stu-id="39a73-136">Set the <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> property to <xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles> as shown in the following configuration example:</span></span>  
  
    ```xml  
    <behaviors>  
      <serviceBehaviors>  
      <behavior name="SvcBehavior1">  
      <serviceAuthorization principalPermissionMode="UseAspNetRoles" />  
      </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    ```  
  
     <span data-ttu-id="39a73-137">Establecer este valor en `UseAspNetRoles` indica que la propiedad `Name` del `PrincipalPermissionAttribute` se utilizará para realizar una comparación de cadenas.</span><span class="sxs-lookup"><span data-stu-id="39a73-137">Setting this value to `UseAspNetRoles` indicates that the `Name` property of the `PrincipalPermissionAttribute` will be used to perform a string comparison.</span></span> <span data-ttu-id="39a73-138">Cuando se usa un certificado como credencial de cliente, WCF concatena de forma predeterminada el nombre común del certificado y la huella digital con un punto y coma para crear un valor único para la identidad principal del cliente.</span><span class="sxs-lookup"><span data-stu-id="39a73-138">When a certificate is used as a client credential, by default WCF concatenates the certificate common name and the thumbprint with a semicolon to create a unique value for the client's primary identity.</span></span> <span data-ttu-id="39a73-139">Con `UseAspNetRoles` establecido como `PrincipalPermissionMode` en el servicio, este valor de identidad primaria se compara con el valor de la propiedad `Name` para determinar los derechos de acceso del usuario.</span><span class="sxs-lookup"><span data-stu-id="39a73-139">With `UseAspNetRoles` set as the `PrincipalPermissionMode` on the service, this primary identity value is compared with the `Name` property value to determine the access rights of the user.</span></span>  
  
     <span data-ttu-id="39a73-140">Alternativamente, al crear un servicio autohospedado, establezca la propiedad <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> en código como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="39a73-140">Alternatively, when creating a self-hosted service, set the <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> property in code as shown in the following code:</span></span>  
  
     [!code-csharp[c_PrincipalPermissionAttribute#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_principalpermissionattribute/cs/source.cs#3)]
     [!code-vb[c_PrincipalPermissionAttribute#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_principalpermissionattribute/vb/source.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="39a73-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="39a73-141">See also</span></span>

- <xref:System.Security.Permissions.PrincipalPermissionAttribute>
- <xref:System.Security.Permissions.SecurityAction.Demand>
- <xref:System.Security.Permissions.PrincipalPermissionAttribute.Role%2A>
- [<span data-ttu-id="39a73-142">Autorización de acceso a operaciones de servicio</span><span class="sxs-lookup"><span data-stu-id="39a73-142">Authorizing Access to Service Operations</span></span>](./samples/authorizing-access-to-service-operations.md)
- [<span data-ttu-id="39a73-143">Información general sobre seguridad</span><span class="sxs-lookup"><span data-stu-id="39a73-143">Security Overview</span></span>](./feature-details/security-overview.md)
- [<span data-ttu-id="39a73-144">Implementación de contratos de servicio</span><span class="sxs-lookup"><span data-stu-id="39a73-144">Implementing Service Contracts</span></span>](implementing-service-contracts.md)
