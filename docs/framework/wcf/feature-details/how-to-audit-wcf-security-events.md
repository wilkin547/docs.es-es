---
title: Cómo auditar los eventos de seguridad de Windows Communication Foundation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [WCF], auditing events
ms.assetid: e71e9587-3336-46a2-9a9e-d72a1743ecec
ms.openlocfilehash: b96c68c06099db2f396d16772cfaa8aee37390fe
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2019
ms.locfileid: "74838018"
---
# <a name="how-to-audit-windows-communication-foundation-security-events"></a><span data-ttu-id="d85fd-102">Cómo auditar los eventos de seguridad de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="d85fd-102">How to: Audit Windows Communication Foundation Security Events</span></span>
<span data-ttu-id="d85fd-103">Windows Communication Foundation (WCF) permite registrar eventos de seguridad en el registro de eventos de Windows, que se pueden ver mediante el Visor de eventos de Windows.</span><span class="sxs-lookup"><span data-stu-id="d85fd-103">Windows Communication Foundation (WCF) allows you to log security events to the Windows event log, which can be viewed using the Windows Event Viewer.</span></span> <span data-ttu-id="d85fd-104">Este tema explica cómo configurar una aplicación para que registre los eventos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="d85fd-104">This topic explains how to set up an application so that it logs security events.</span></span> <span data-ttu-id="d85fd-105">Para obtener más información acerca de la auditoría de WCF, vea [Auditoría](../../../../docs/framework/wcf/feature-details/auditing-security-events.md).</span><span class="sxs-lookup"><span data-stu-id="d85fd-105">For more information about WCF auditing, see [Auditing](../../../../docs/framework/wcf/feature-details/auditing-security-events.md).</span></span>  
  
### <a name="to-audit-security-events-in-code"></a><span data-ttu-id="d85fd-106">Para auditar los eventos de seguridad en el código</span><span class="sxs-lookup"><span data-stu-id="d85fd-106">To audit security events in code</span></span>  
  
1. <span data-ttu-id="d85fd-107">Especifique la ubicación del registro de auditoría.</span><span class="sxs-lookup"><span data-stu-id="d85fd-107">Specify the audit log location.</span></span> <span data-ttu-id="d85fd-108">Para ello, establezca la propiedad <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.AuditLogLocation%2A> de la clase <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> en uno de los valores de enumeración <xref:System.ServiceModel.AuditLogLocation>, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="d85fd-108">To do this, set the <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.AuditLogLocation%2A> property of the <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> class to one of the <xref:System.ServiceModel.AuditLogLocation> enumeration values, as shown in the following code.</span></span>  
  
     [!code-csharp[AuditingSecurityEvents#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/auditingsecurityevents/cs/auditingsecurityevents.cs#2)]
     [!code-vb[AuditingSecurityEvents#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/auditingsecurityevents/vb/auditingsecurityevents.vb#2)]  
  
     <span data-ttu-id="d85fd-109">La enumeración <xref:System.ServiceModel.AuditLogLocation> tiene tres valores: `Application`, `Security`o `Default`.</span><span class="sxs-lookup"><span data-stu-id="d85fd-109">The <xref:System.ServiceModel.AuditLogLocation> enumeration has three values: `Application`, `Security`, or `Default`.</span></span> <span data-ttu-id="d85fd-110">El valor especifica uno de los registros visibles en el visor de eventos, el registro de seguridad o de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="d85fd-110">The value specifies one of the logs visible in the Event Viewer, either the Security log or the Application log.</span></span> <span data-ttu-id="d85fd-111">Si utiliza el valor `Default`, el registro real dependerá del sistema operativo en el que se está ejecutando la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d85fd-111">If you use the `Default` value, the actual log will depend on the operating system the application is running on.</span></span> <span data-ttu-id="d85fd-112">Si se habilita la auditoría y no se especifica la ubicación del registro, el valor predeterminado es el registro de `Security` en las plataformas que admiten escribir en el registro de seguridad; de lo contrario, se escribirá en el registro `Application`.</span><span class="sxs-lookup"><span data-stu-id="d85fd-112">If auditing is enabled and the log location is not specified, the default is the `Security` log for platforms that support writing to the Security log; otherwise, it will write to the `Application` log.</span></span> <span data-ttu-id="d85fd-113">Solo [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] y Windows Vista admiten la escritura en el registro de seguridad de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="d85fd-113">Only [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] and Windows Vista support writing to the Security log by default.</span></span>  
  
2. <span data-ttu-id="d85fd-114">Establezca los tipos de eventos que se van a auditar.</span><span class="sxs-lookup"><span data-stu-id="d85fd-114">Set up the types of events to audit.</span></span> <span data-ttu-id="d85fd-115">Puede auditar, simultáneamente, eventos de nivel de servicio o eventos de nivel de autorización.</span><span class="sxs-lookup"><span data-stu-id="d85fd-115">You can simultaneously audit service-level events or message-level authorization events.</span></span> <span data-ttu-id="d85fd-116">Establezca la propiedad <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.ServiceAuthorizationAuditLevel%2A> o la propiedad <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.MessageAuthenticationAuditLevel%2A> en uno de los valores de enumeración <xref:System.ServiceModel.AuditLevel>, como muestra el siguiente código.</span><span class="sxs-lookup"><span data-stu-id="d85fd-116">To do this, set the <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.ServiceAuthorizationAuditLevel%2A> property or the <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.MessageAuthenticationAuditLevel%2A> property to one of the <xref:System.ServiceModel.AuditLevel> enumeration values, as shown in the following code.</span></span>  
  
     [!code-csharp[AuditingSecurityEvents#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/auditingsecurityevents/cs/auditingsecurityevents.cs#3)]
     [!code-vb[AuditingSecurityEvents#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/auditingsecurityevents/vb/auditingsecurityevents.vb#3)]  
  
3. <span data-ttu-id="d85fd-117">Especifique si suprimir o exponer los errores a la aplicación relacionados con los eventos de auditoría del registro.</span><span class="sxs-lookup"><span data-stu-id="d85fd-117">Specify whether to suppress or expose failures to the application regarding log audit events.</span></span> <span data-ttu-id="d85fd-118">Establezca la propiedad <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.SuppressAuditFailure%2A> en `true` o `false`, como muestra el siguiente código.</span><span class="sxs-lookup"><span data-stu-id="d85fd-118">Set the <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.SuppressAuditFailure%2A> property to either `true` or `false`, as shown in the following code.</span></span>  
  
     [!code-csharp[AuditingSecurityEvents#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/auditingsecurityevents/cs/auditingsecurityevents.cs#4)]
     [!code-vb[AuditingSecurityEvents#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/auditingsecurityevents/vb/auditingsecurityevents.vb#4)]  
  
     <span data-ttu-id="d85fd-119">La propiedad `SuppressAuditFailure` predeterminada es `true`, de modo que el error que se audita no afecta a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d85fd-119">The default `SuppressAuditFailure` property is `true`, so that the failure to audit does not affect the application.</span></span> <span data-ttu-id="d85fd-120">De lo contrario, se producirá una excepción.</span><span class="sxs-lookup"><span data-stu-id="d85fd-120">Otherwise, an exception is thrown.</span></span> <span data-ttu-id="d85fd-121">Para cualquier auditoría realizada correctamente, se escribe con detalle el seguimiento de la traza.</span><span class="sxs-lookup"><span data-stu-id="d85fd-121">For any successful audit, a verbose trace is written.</span></span> <span data-ttu-id="d85fd-122">Para cualquier error que se audita, se escribe el seguimiento de la traza en el nivel del error.</span><span class="sxs-lookup"><span data-stu-id="d85fd-122">For any failure to audit, the trace is written at the Error level.</span></span>  
  
4. <span data-ttu-id="d85fd-123">Elimine el <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> existente de la colección de comportamientos encontrada en la descripción de <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="d85fd-123">Delete the existing <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> from the collection of behaviors found in the description of a <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="d85fd-124">A la colección de comportamiento tiene acceso la propiedad <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A>, a la que a su vez tiene acceso la propiedad <xref:System.ServiceModel.ServiceHostBase.Description%2A>.</span><span class="sxs-lookup"><span data-stu-id="d85fd-124">The behavior collection is accessed by the <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> property, which in turn is accessed from the <xref:System.ServiceModel.ServiceHostBase.Description%2A> property.</span></span> <span data-ttu-id="d85fd-125">A continuación, agregue el nuevo <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> a la misma colección, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="d85fd-125">Then add the new <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> to the same collection, as shown in the following code.</span></span>  
  
     [!code-csharp[AuditingSecurityEvents#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/auditingsecurityevents/cs/auditingsecurityevents.cs#5)]
     [!code-vb[AuditingSecurityEvents#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/auditingsecurityevents/vb/auditingsecurityevents.vb#5)]  
  
### <a name="to-set-up-auditing-in-configuration"></a><span data-ttu-id="d85fd-126">Para establecer la auditoría en la configuración</span><span class="sxs-lookup"><span data-stu-id="d85fd-126">To set up auditing in configuration</span></span>  
  
1. <span data-ttu-id="d85fd-127">Para configurar la auditoría en la configuración, agregue un elemento [\<behavior >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) a la sección [\<Behaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) del archivo Web. config.</span><span class="sxs-lookup"><span data-stu-id="d85fd-127">To set up auditing in configuration, add a [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) element to the [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) section of the web.config file.</span></span> <span data-ttu-id="d85fd-128">Después, agregue un elemento [\<serviceSecurityAudit >](../../../../docs/framework/configure-apps/file-schema/wcf/servicesecurityaudit.md) y establezca los distintos atributos, tal y como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="d85fd-128">Then add a [\<serviceSecurityAudit>](../../../../docs/framework/configure-apps/file-schema/wcf/servicesecurityaudit.md) element and set the various attributes, as shown in the following example.</span></span>  
  
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
  
2. <span data-ttu-id="d85fd-129">Debe especificarse el comportamiento del servicio, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="d85fd-129">You must specify the behavior for the service, as shown in the following example.</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="d85fd-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d85fd-130">Example</span></span>  
 <span data-ttu-id="d85fd-131">El siguiente código crea una instancia de la clase <xref:System.ServiceModel.ServiceHost> y agrega un nuevo <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> a la colección de comportamientos.</span><span class="sxs-lookup"><span data-stu-id="d85fd-131">The following code creates an instance of the <xref:System.ServiceModel.ServiceHost> class and adds a new <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> to its collection of behaviors.</span></span>  
  
 [!code-csharp[AuditingSecurityEvents#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/auditingsecurityevents/cs/auditingsecurityevents.cs#1)]
 [!code-vb[AuditingSecurityEvents#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/auditingsecurityevents/vb/auditingsecurityevents.vb#1)]  
  
## <a name="net-framework-security"></a><span data-ttu-id="d85fd-132">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="d85fd-132">.NET Framework Security</span></span>  
 <span data-ttu-id="d85fd-133">Cuando se establece la propiedad <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.SuppressAuditFailure%2A> como `true`, se suprime cualquier error que genere auditorías de seguridad (si se establece como `false`, se inicia una excepción).</span><span class="sxs-lookup"><span data-stu-id="d85fd-133">Setting the <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.SuppressAuditFailure%2A> property to `true`, suppresses any failure to generate security audits (if set to `false`, an exception is thrown).</span></span> <span data-ttu-id="d85fd-134">Sin embargo, si habilita la siguiente propiedad de **configuración de seguridad local** de Windows, un error al generar eventos de auditoría hará que Windows se cierre inmediatamente:</span><span class="sxs-lookup"><span data-stu-id="d85fd-134">However, if you enable the following Windows **Local Security Setting** property, a failure to generate audit events will cause Windows to shut down immediately:</span></span>  
  
 <span data-ttu-id="d85fd-135">**Auditoría: apagar el sistema inmediatamente si no se pueden registrar las auditorías de seguridad**</span><span class="sxs-lookup"><span data-stu-id="d85fd-135">**Audit: Shut down system immediately if unable to log security audits**</span></span>  
  
 <span data-ttu-id="d85fd-136">Para establecer la propiedad, abra el cuadro de diálogo **configuración de seguridad local** .</span><span class="sxs-lookup"><span data-stu-id="d85fd-136">To set the property, open the **Local Security Settings** dialog box.</span></span> <span data-ttu-id="d85fd-137">En **configuración de seguridad**, haga clic en **Directivas locales**.</span><span class="sxs-lookup"><span data-stu-id="d85fd-137">Under **Security Settings**, click **Local Policies**.</span></span> <span data-ttu-id="d85fd-138">A continuación, haga clic en **Opciones de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="d85fd-138">Then click **Security Options**.</span></span>  
  
 <span data-ttu-id="d85fd-139">Si la propiedad <xref:System.ServiceModel.AuditLogLocation> está establecida en <xref:System.ServiceModel.AuditLogLocation.Security> y **auditar el acceso a objetos** no está establecido en la **Directiva de seguridad local**, los eventos de auditoría no se escribirán en el registro de seguridad.</span><span class="sxs-lookup"><span data-stu-id="d85fd-139">If the <xref:System.ServiceModel.AuditLogLocation> property is set to <xref:System.ServiceModel.AuditLogLocation.Security> and **Audit Object Access** is not set in the **Local Security Policy**, audit events will not be written to the Security log.</span></span> <span data-ttu-id="d85fd-140">Tenga en cuenta que no se devuelve ningún error, aunque las entradas de auditoría no se escriben en el registro de seguridad.</span><span class="sxs-lookup"><span data-stu-id="d85fd-140">Note that no failure is returned, but audit entries are not written to the Security log.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d85fd-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="d85fd-141">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.AuditLogLocation%2A>
- <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>
- <xref:System.ServiceModel.AuditLogLocation>
- [<span data-ttu-id="d85fd-142">Auditoría</span><span class="sxs-lookup"><span data-stu-id="d85fd-142">Auditing</span></span>](../../../../docs/framework/wcf/feature-details/auditing-security-events.md)
