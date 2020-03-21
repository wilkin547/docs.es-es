---
title: Cómo auditar los eventos de seguridad de Windows Communication Foundation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [WCF], auditing events
ms.assetid: e71e9587-3336-46a2-9a9e-d72a1743ecec
ms.openlocfilehash: 62d26b24b5d46427c1871fccf48b063c45781beb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185124"
---
# <a name="how-to-audit-windows-communication-foundation-security-events"></a><span data-ttu-id="e0226-102">Cómo auditar los eventos de seguridad de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="e0226-102">How to: Audit Windows Communication Foundation Security Events</span></span>
<span data-ttu-id="e0226-103">Windows Communication Foundation (WCF) permite registrar eventos de seguridad en el registro de eventos de Windows, que se puede ver mediante el Visor de eventos de Windows.</span><span class="sxs-lookup"><span data-stu-id="e0226-103">Windows Communication Foundation (WCF) allows you to log security events to the Windows event log, which can be viewed using the Windows Event Viewer.</span></span> <span data-ttu-id="e0226-104">Este tema explica cómo configurar una aplicación para que registre los eventos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="e0226-104">This topic explains how to set up an application so that it logs security events.</span></span> <span data-ttu-id="e0226-105">Para obtener más información acerca de la auditoría DE WCF, vea [auditoría](../../../../docs/framework/wcf/feature-details/auditing-security-events.md).</span><span class="sxs-lookup"><span data-stu-id="e0226-105">For more information about WCF auditing, see [Auditing](../../../../docs/framework/wcf/feature-details/auditing-security-events.md).</span></span>  
  
### <a name="to-audit-security-events-in-code"></a><span data-ttu-id="e0226-106">Para auditar los eventos de seguridad en el código</span><span class="sxs-lookup"><span data-stu-id="e0226-106">To audit security events in code</span></span>  
  
1. <span data-ttu-id="e0226-107">Especifique la ubicación del registro de auditoría.</span><span class="sxs-lookup"><span data-stu-id="e0226-107">Specify the audit log location.</span></span> <span data-ttu-id="e0226-108">Para ello, establezca la propiedad <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.AuditLogLocation%2A> de la clase <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> en uno de los valores de enumeración <xref:System.ServiceModel.AuditLogLocation>, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="e0226-108">To do this, set the <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.AuditLogLocation%2A> property of the <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> class to one of the <xref:System.ServiceModel.AuditLogLocation> enumeration values, as shown in the following code.</span></span>  
  
     [!code-csharp[AuditingSecurityEvents#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/auditingsecurityevents/cs/auditingsecurityevents.cs#2)]
     [!code-vb[AuditingSecurityEvents#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/auditingsecurityevents/vb/auditingsecurityevents.vb#2)]  
  
     <span data-ttu-id="e0226-109">La <xref:System.ServiceModel.AuditLogLocation> enumeración tiene `Application` `Security`tres `Default`valores: , , o .</span><span class="sxs-lookup"><span data-stu-id="e0226-109">The <xref:System.ServiceModel.AuditLogLocation> enumeration has three values: `Application`, `Security`, or `Default`.</span></span> <span data-ttu-id="e0226-110">El valor especifica uno de los registros visibles en el visor de eventos, el registro de seguridad o de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="e0226-110">The value specifies one of the logs visible in the Event Viewer, either the Security log or the Application log.</span></span> <span data-ttu-id="e0226-111">Si utiliza el valor `Default`, el registro real dependerá del sistema operativo en el que se está ejecutando la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e0226-111">If you use the `Default` value, the actual log will depend on the operating system the application is running on.</span></span> <span data-ttu-id="e0226-112">Si se habilita la auditoría y no se especifica la ubicación del registro, el valor predeterminado es el registro de `Security` en las plataformas que admiten escribir en el registro de seguridad; de lo contrario, se escribirá en el registro `Application`.</span><span class="sxs-lookup"><span data-stu-id="e0226-112">If auditing is enabled and the log location is not specified, the default is the `Security` log for platforms that support writing to the Security log; otherwise, it will write to the `Application` log.</span></span> <span data-ttu-id="e0226-113">Solo Windows Server 2003 y Windows Vista admiten la escritura en el registro de seguridad de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e0226-113">Only Windows Server 2003 and Windows Vista support writing to the Security log by default.</span></span>  
  
2. <span data-ttu-id="e0226-114">Establezca los tipos de eventos que se van a auditar.</span><span class="sxs-lookup"><span data-stu-id="e0226-114">Set up the types of events to audit.</span></span> <span data-ttu-id="e0226-115">Puede auditar, simultáneamente, eventos de nivel de servicio o eventos de nivel de autorización.</span><span class="sxs-lookup"><span data-stu-id="e0226-115">You can simultaneously audit service-level events or message-level authorization events.</span></span> <span data-ttu-id="e0226-116">Establezca la propiedad <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.ServiceAuthorizationAuditLevel%2A> o la propiedad <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.MessageAuthenticationAuditLevel%2A> en uno de los valores de enumeración <xref:System.ServiceModel.AuditLevel>, como muestra el siguiente código.</span><span class="sxs-lookup"><span data-stu-id="e0226-116">To do this, set the <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.ServiceAuthorizationAuditLevel%2A> property or the <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.MessageAuthenticationAuditLevel%2A> property to one of the <xref:System.ServiceModel.AuditLevel> enumeration values, as shown in the following code.</span></span>  
  
     [!code-csharp[AuditingSecurityEvents#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/auditingsecurityevents/cs/auditingsecurityevents.cs#3)]
     [!code-vb[AuditingSecurityEvents#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/auditingsecurityevents/vb/auditingsecurityevents.vb#3)]  
  
3. <span data-ttu-id="e0226-117">Especifique si suprimir o exponer los errores a la aplicación relacionados con los eventos de auditoría del registro.</span><span class="sxs-lookup"><span data-stu-id="e0226-117">Specify whether to suppress or expose failures to the application regarding log audit events.</span></span> <span data-ttu-id="e0226-118">Establezca la propiedad <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.SuppressAuditFailure%2A> en `true` o `false`, como muestra el siguiente código.</span><span class="sxs-lookup"><span data-stu-id="e0226-118">Set the <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.SuppressAuditFailure%2A> property to either `true` or `false`, as shown in the following code.</span></span>  
  
     [!code-csharp[AuditingSecurityEvents#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/auditingsecurityevents/cs/auditingsecurityevents.cs#4)]
     [!code-vb[AuditingSecurityEvents#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/auditingsecurityevents/vb/auditingsecurityevents.vb#4)]  
  
     <span data-ttu-id="e0226-119">La propiedad `SuppressAuditFailure` predeterminada es `true`, de modo que el error que se audita no afecta a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e0226-119">The default `SuppressAuditFailure` property is `true`, so that the failure to audit does not affect the application.</span></span> <span data-ttu-id="e0226-120">De lo contrario, se inicia una excepción.</span><span class="sxs-lookup"><span data-stu-id="e0226-120">Otherwise, an exception is thrown.</span></span> <span data-ttu-id="e0226-121">Para cualquier auditoría realizada correctamente, se escribe con detalle el seguimiento de la traza.</span><span class="sxs-lookup"><span data-stu-id="e0226-121">For any successful audit, a verbose trace is written.</span></span> <span data-ttu-id="e0226-122">Para cualquier error que se audita, se escribe el seguimiento de la traza en el nivel del error.</span><span class="sxs-lookup"><span data-stu-id="e0226-122">For any failure to audit, the trace is written at the Error level.</span></span>  
  
4. <span data-ttu-id="e0226-123">Elimine el <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> existente de la colección de comportamientos encontrada en la descripción de <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="e0226-123">Delete the existing <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> from the collection of behaviors found in the description of a <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="e0226-124">A la colección de comportamiento tiene acceso la propiedad <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A>, a la que a su vez tiene acceso la propiedad <xref:System.ServiceModel.ServiceHostBase.Description%2A>.</span><span class="sxs-lookup"><span data-stu-id="e0226-124">The behavior collection is accessed by the <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> property, which in turn is accessed from the <xref:System.ServiceModel.ServiceHostBase.Description%2A> property.</span></span> <span data-ttu-id="e0226-125">A continuación, agregue el nuevo <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> a la misma colección, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="e0226-125">Then add the new <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> to the same collection, as shown in the following code.</span></span>  
  
     [!code-csharp[AuditingSecurityEvents#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/auditingsecurityevents/cs/auditingsecurityevents.cs#5)]
     [!code-vb[AuditingSecurityEvents#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/auditingsecurityevents/vb/auditingsecurityevents.vb#5)]  
  
### <a name="to-set-up-auditing-in-configuration"></a><span data-ttu-id="e0226-126">Para establecer la auditoría en la configuración</span><span class="sxs-lookup"><span data-stu-id="e0226-126">To set up auditing in configuration</span></span>  
  
1. <span data-ttu-id="e0226-127">Para configurar la auditoría en [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) la configuración, agregue un elemento de comportamiento>a los [ \<comportamientos>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) sección del archivo web.config.</span><span class="sxs-lookup"><span data-stu-id="e0226-127">To set up auditing in configuration, add a [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) element to the [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) section of the web.config file.</span></span> <span data-ttu-id="e0226-128">A continuación, agregue un [ \<elemento de>serviceSecurityAudit](../../../../docs/framework/configure-apps/file-schema/wcf/servicesecurityaudit.md) y establezca los distintos atributos, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="e0226-128">Then add a [\<serviceSecurityAudit>](../../../../docs/framework/configure-apps/file-schema/wcf/servicesecurityaudit.md) element and set the various attributes, as shown in the following example.</span></span>  
  
    ```xml  
    <behaviors>  
       <behavior name="myAuditBehavior">  
          <serviceSecurityAudit auditLogLocation="Application"  
                suppressAuditFailure="false"
                serviceAuthorizationAuditLevel="None"
                messageAuthenticationAuditLevel="SuccessOrFailure" />  
          </behavior>  
    </behaviors>  
    ```  
  
2. <span data-ttu-id="e0226-129">Debe especificarse el comportamiento del servicio, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="e0226-129">You must specify the behavior for the service, as shown in the following example.</span></span>  
  
    ```xml  
    <services>  
        <service type="WCS.Samples.Service.Echo"
        behaviorConfiguration=" myAuditBehavior">  
           <endpoint address=""  
                    binding="wsHttpBinding"  
                    bindingConfiguration="CertificateDefault"
                    contract="WCS.Samples.Service.IEcho" />  
        </service>  
    </services>  
    ```  
  
## <a name="example"></a><span data-ttu-id="e0226-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e0226-130">Example</span></span>  
 <span data-ttu-id="e0226-131">El siguiente código crea una instancia de la clase <xref:System.ServiceModel.ServiceHost> y agrega un nuevo <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> a la colección de comportamientos.</span><span class="sxs-lookup"><span data-stu-id="e0226-131">The following code creates an instance of the <xref:System.ServiceModel.ServiceHost> class and adds a new <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> to its collection of behaviors.</span></span>  
  
 [!code-csharp[AuditingSecurityEvents#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/auditingsecurityevents/cs/auditingsecurityevents.cs#1)]
 [!code-vb[AuditingSecurityEvents#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/auditingsecurityevents/vb/auditingsecurityevents.vb#1)]  
  
## <a name="net-framework-security"></a><span data-ttu-id="e0226-132">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="e0226-132">.NET Framework Security</span></span>  
 <span data-ttu-id="e0226-133">Cuando se establece la propiedad <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.SuppressAuditFailure%2A> como `true`, se suprime cualquier error que genere auditorías de seguridad (si se establece como `false`, se inicia una excepción).</span><span class="sxs-lookup"><span data-stu-id="e0226-133">Setting the <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.SuppressAuditFailure%2A> property to `true`, suppresses any failure to generate security audits (if set to `false`, an exception is thrown).</span></span> <span data-ttu-id="e0226-134">Sin embargo, si habilita la siguiente propiedad Configuración de **seguridad local** de Windows, un error al generar eventos de auditoría hará que Windows se cierre inmediatamente:</span><span class="sxs-lookup"><span data-stu-id="e0226-134">However, if you enable the following Windows **Local Security Setting** property, a failure to generate audit events will cause Windows to shut down immediately:</span></span>  
  
 <span data-ttu-id="e0226-135">**Auditoría: apagar el sistema de inmediato si no se pueden registrar las auditorías de seguridad**</span><span class="sxs-lookup"><span data-stu-id="e0226-135">**Audit: Shut down system immediately if unable to log security audits**</span></span>  
  
 <span data-ttu-id="e0226-136">Para establecer la propiedad, abra el cuadro de diálogo Configuración de **seguridad local.**</span><span class="sxs-lookup"><span data-stu-id="e0226-136">To set the property, open the **Local Security Settings** dialog box.</span></span> <span data-ttu-id="e0226-137">En **Configuración de seguridad**, haga clic en **Directivas locales**.</span><span class="sxs-lookup"><span data-stu-id="e0226-137">Under **Security Settings**, click **Local Policies**.</span></span> <span data-ttu-id="e0226-138">A continuación, haga clic en **Opciones de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="e0226-138">Then click **Security Options**.</span></span>  
  
 <span data-ttu-id="e0226-139">Si <xref:System.ServiceModel.AuditLogLocation> la propiedad <xref:System.ServiceModel.AuditLogLocation.Security> está establecida en y **Audit Object Access** no está establecido en la directiva de seguridad **local,** los eventos de auditoría no se escribirán en el registro de seguridad.</span><span class="sxs-lookup"><span data-stu-id="e0226-139">If the <xref:System.ServiceModel.AuditLogLocation> property is set to <xref:System.ServiceModel.AuditLogLocation.Security> and **Audit Object Access** is not set in the **Local Security Policy**, audit events will not be written to the Security log.</span></span> <span data-ttu-id="e0226-140">Tenga en cuenta que no se devuelve ningún error, aunque las entradas de auditoría no se escriben en el registro de seguridad.</span><span class="sxs-lookup"><span data-stu-id="e0226-140">Note that no failure is returned, but audit entries are not written to the Security log.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0226-141">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e0226-141">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.AuditLogLocation%2A>
- <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>
- <xref:System.ServiceModel.AuditLogLocation>
- [<span data-ttu-id="e0226-142">Auditoría</span><span class="sxs-lookup"><span data-stu-id="e0226-142">Auditing</span></span>](../../../../docs/framework/wcf/feature-details/auditing-security-events.md)
