---
title: Escenarios de seguridad comunes
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: security [WCF], scenarios
ms.assetid: 201923b5-5162-4a8a-8d4c-e7bd242748d5
caps.latest.revision: "18"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: d8881768d66e95ce1391ce1be1663bdc3107a347
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="common-security-scenarios"></a><span data-ttu-id="f1e96-102">Escenarios de seguridad comunes</span><span class="sxs-lookup"><span data-stu-id="f1e96-102">Common Security Scenarios</span></span>
<span data-ttu-id="f1e96-103">Los temas de esta sección catalogan varias configuraciones posibles de seguridad de cliente y servicio.</span><span class="sxs-lookup"><span data-stu-id="f1e96-103">The topics in this section catalog a number of possible client and service security configurations.</span></span> <span data-ttu-id="f1e96-104">Las configuraciones varían según varios factores.</span><span class="sxs-lookup"><span data-stu-id="f1e96-104">Configurations vary according to a number of factors.</span></span> <span data-ttu-id="f1e96-105">Por ejemplo, si un servicio o cliente está en una intranet o si Windows o transporte (como HTTPS) proporciona la seguridad.</span><span class="sxs-lookup"><span data-stu-id="f1e96-105">For example, whether a service or client is on an intranet, or whether the security is provided by Windows or transport (such as HTTPS).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f1e96-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="f1e96-106">In This Section</span></span>  
 [<span data-ttu-id="f1e96-107">Cliente y servicio de Internet no protegidos</span><span class="sxs-lookup"><span data-stu-id="f1e96-107">Internet Unsecured Client and Service</span></span>](../../../../docs/framework/wcf/feature-details/internet-unsecured-client-and-service.md)  
 <span data-ttu-id="f1e96-108">Un ejemplo de un cliente y servicio público y no protegido.</span><span class="sxs-lookup"><span data-stu-id="f1e96-108">An example of a public, unsecured client and service.</span></span>  
  
 [<span data-ttu-id="f1e96-109">Cliente y servicio de intranet no protegidos</span><span class="sxs-lookup"><span data-stu-id="f1e96-109">Intranet Unsecured Client and Service</span></span>](../../../../docs/framework/wcf/feature-details/intranet-unsecured-client-and-service.md)  
 <span data-ttu-id="f1e96-110">Un servicio básico de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] desarrollado para proporcionar información sobre una red privada segura a una aplicación [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f1e96-110">A basic [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service developed to provide information on a secure private network to a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] application.</span></span>  
  
 [<span data-ttu-id="f1e96-111">Seguridad del transporte con la autenticación básica</span><span class="sxs-lookup"><span data-stu-id="f1e96-111">Transport Security with Basic Authentication</span></span>](../../../../docs/framework/wcf/feature-details/transport-security-with-basic-authentication.md)  
 <span data-ttu-id="f1e96-112">La aplicación permite a los clientes iniciar sesión al utilizar autenticación personalizada.</span><span class="sxs-lookup"><span data-stu-id="f1e96-112">The application allows clients to log on using custom authentication.</span></span>  
  
 [<span data-ttu-id="f1e96-113">Seguridad del transporte con la autenticación de Windows</span><span class="sxs-lookup"><span data-stu-id="f1e96-113">Transport Security with Windows Authentication</span></span>](../../../../docs/framework/wcf/feature-details/transport-security-with-windows-authentication.md)  
 <span data-ttu-id="f1e96-114">Muestra un cliente y servicio protegidos por seguridad de Windows.</span><span class="sxs-lookup"><span data-stu-id="f1e96-114">Shows a client and service secured by Windows security.</span></span>  
  
 [<span data-ttu-id="f1e96-115">Seguridad del transporte con clientes anónimos</span><span class="sxs-lookup"><span data-stu-id="f1e96-115">Transport Security with an Anonymous Client</span></span>](../../../../docs/framework/wcf/feature-details/transport-security-with-an-anonymous-client.md)  
 <span data-ttu-id="f1e96-116">Este escenario utiliza la seguridad de transporte (como HTTPS) para garantizar la confidencialidad y la integridad.</span><span class="sxs-lookup"><span data-stu-id="f1e96-116">This scenario uses transport security (such as HTTPS) to ensure confidentiality and integrity.</span></span>  
  
 [<span data-ttu-id="f1e96-117">Seguridad del transporte con autenticación de certificados</span><span class="sxs-lookup"><span data-stu-id="f1e96-117">Transport Security with Certificate Authentication</span></span>](../../../../docs/framework/wcf/feature-details/transport-security-with-certificate-authentication.md)  
 <span data-ttu-id="f1e96-118">Muestra a un cliente y servicio protegidos por un certificado.</span><span class="sxs-lookup"><span data-stu-id="f1e96-118">Shows a client and service secured by a certificate.</span></span>  
  
 [<span data-ttu-id="f1e96-119">Seguridad de mensajes con clientes anónimos</span><span class="sxs-lookup"><span data-stu-id="f1e96-119">Message Security with an Anonymous Client</span></span>](../../../../docs/framework/wcf/feature-details/message-security-with-an-anonymous-client.md)  
 <span data-ttu-id="f1e96-120">Muestra un cliente y el servicio protegido por el modo de seguridad de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f1e96-120">Shows a client and service secured by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] message security.</span></span>  
  
 [<span data-ttu-id="f1e96-121">Seguridad de mensajes con un cliente de nombres de usuario</span><span class="sxs-lookup"><span data-stu-id="f1e96-121">Message Security with a User Name Client</span></span>](../../../../docs/framework/wcf/feature-details/message-security-with-a-user-name-client.md)  
 <span data-ttu-id="f1e96-122">El cliente es una aplicación de Windows Forms que permite a los clientes iniciar sesión al utilizar un nombre de usuario y contraseña del dominio.</span><span class="sxs-lookup"><span data-stu-id="f1e96-122">The client is a Windows Forms application that allows clients to log on using a domain user name and password.</span></span>  
  
 [<span data-ttu-id="f1e96-123">Seguridad de mensajes con un cliente de certificado</span><span class="sxs-lookup"><span data-stu-id="f1e96-123">Message Security with a Certificate Client</span></span>](../../../../docs/framework/wcf/feature-details/message-security-with-a-certificate-client.md)  
 <span data-ttu-id="f1e96-124">Los servidores tienen certificados y cada cliente tiene un certificado.</span><span class="sxs-lookup"><span data-stu-id="f1e96-124">Servers have certificates, and each client has a certificate.</span></span> <span data-ttu-id="f1e96-125">Un contexto de seguridad se establece a través de la negociación de Seguridad de la capa de transporte (TLS).</span><span class="sxs-lookup"><span data-stu-id="f1e96-125">A security context is established through Transport Layer Security (TLS) negotiation.</span></span>  
  
 [<span data-ttu-id="f1e96-126">Seguridad de mensajes con un cliente de Windows</span><span class="sxs-lookup"><span data-stu-id="f1e96-126">Message Security with a Windows Client</span></span>](../../../../docs/framework/wcf/feature-details/message-security-with-a-windows-client.md)  
 <span data-ttu-id="f1e96-127">Una variación del cliente del certificado.</span><span class="sxs-lookup"><span data-stu-id="f1e96-127">A variation of the certificate client.</span></span> <span data-ttu-id="f1e96-128">Los servidores tienen certificados y cada cliente tiene un certificado.</span><span class="sxs-lookup"><span data-stu-id="f1e96-128">Servers have certificates, and each client has a certificate.</span></span> <span data-ttu-id="f1e96-129">Un contexto de seguridad se establece a través de la negociación de TLS.</span><span class="sxs-lookup"><span data-stu-id="f1e96-129">A security context is established through TLS negotiation.</span></span>  
  
 [<span data-ttu-id="f1e96-130">Seguridad de mensajes con un cliente de Windows sin negociación de credenciales</span><span class="sxs-lookup"><span data-stu-id="f1e96-130">Message Security with a Windows Client without Credential Negotiation</span></span>](../../../../docs/framework/wcf/feature-details/message-security-with-a-windows-client-without-credential-negotiation.md)  
 <span data-ttu-id="f1e96-131">Muestra un cliente y el servicio protegidos por un dominio de Kerberos.</span><span class="sxs-lookup"><span data-stu-id="f1e96-131">Shows a client and service secured by a Kerberos domain.</span></span>  
  
 [<span data-ttu-id="f1e96-132">Seguridad de mensajes con certificados mutuos</span><span class="sxs-lookup"><span data-stu-id="f1e96-132">Message Security with Mutual Certificates</span></span>](../../../../docs/framework/wcf/feature-details/message-security-with-mutual-certificates.md)  
 <span data-ttu-id="f1e96-133">Los servidores tienen certificados y cada cliente tiene un certificado.</span><span class="sxs-lookup"><span data-stu-id="f1e96-133">Servers have certificates, and each client has a certificate.</span></span> <span data-ttu-id="f1e96-134">El certificado de servidor se distribuye con la aplicación y está disponible fuera de banda.</span><span class="sxs-lookup"><span data-stu-id="f1e96-134">The server certificate is distributed with the application and is available out of band.</span></span>  
  
 [<span data-ttu-id="f1e96-135">Seguridad de mensajes con tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="f1e96-135">Message Security with Issued Tokens</span></span>](../../../../docs/framework/wcf/feature-details/message-security-with-issued-tokens.md)  
 <span data-ttu-id="f1e96-136">La seguridad federada que permite el establecimiento de confianza entre dominios independientes.</span><span class="sxs-lookup"><span data-stu-id="f1e96-136">Federated security that enables the establishment of trust between independent domains.</span></span>  
  
 [<span data-ttu-id="f1e96-137">Subsistema de confianza</span><span class="sxs-lookup"><span data-stu-id="f1e96-137">Trusted Subsystem</span></span>](../../../../docs/framework/wcf/feature-details/trusted-subsystem.md)  
 <span data-ttu-id="f1e96-138">Un cliente obtiene acceso a uno o varios servicios Web distribuidos a través de una red.</span><span class="sxs-lookup"><span data-stu-id="f1e96-138">A client accesses one or more Web services that are distributed across a network.</span></span> <span data-ttu-id="f1e96-139">Los servicios Web tienen acceso a recursos adicionales (como bases de datos u otros servicios Web) que se deben proteger.</span><span class="sxs-lookup"><span data-stu-id="f1e96-139">The Web services access additional resources (such as databases or other Web services) that must be secured.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="f1e96-140">Referencia</span><span class="sxs-lookup"><span data-stu-id="f1e96-140">Reference</span></span>  
 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a><span data-ttu-id="f1e96-141">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="f1e96-141">Related Sections</span></span>  
 [<span data-ttu-id="f1e96-142">Autorización</span><span class="sxs-lookup"><span data-stu-id="f1e96-142">Authorization</span></span>](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
  
 [<span data-ttu-id="f1e96-143">Información general sobre seguridad</span><span class="sxs-lookup"><span data-stu-id="f1e96-143">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
  
 [<span data-ttu-id="f1e96-144">Seguridad</span><span class="sxs-lookup"><span data-stu-id="f1e96-144">Security</span></span>](../../../../docs/framework/wcf/feature-details/security.md)  
  
 [<span data-ttu-id="f1e96-145">Enlaces y seguridad</span><span class="sxs-lookup"><span data-stu-id="f1e96-145">Bindings and Security</span></span>](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)  
  
 [<span data-ttu-id="f1e96-146">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="f1e96-146">Securing Services and Clients</span></span>](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
  
 [<span data-ttu-id="f1e96-147">Autenticación</span><span class="sxs-lookup"><span data-stu-id="f1e96-147">Authentication</span></span>](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)  
  
 [<span data-ttu-id="f1e96-148">Autorización</span><span class="sxs-lookup"><span data-stu-id="f1e96-148">Authorization</span></span>](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
  
 [<span data-ttu-id="f1e96-149">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="f1e96-149">Federation and Issued Tokens</span></span>](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
  
 [<span data-ttu-id="f1e96-150">Auditoría</span><span class="sxs-lookup"><span data-stu-id="f1e96-150">Auditing</span></span>](../../../../docs/framework/wcf/feature-details/auditing-security-events.md)  
  
## <a name="see-also"></a><span data-ttu-id="f1e96-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="f1e96-151">See Also</span></span>  
 [<span data-ttu-id="f1e96-152">Orientación de seguridad y procedimientos recomendados</span><span class="sxs-lookup"><span data-stu-id="f1e96-152">Security Guidance and Best Practices</span></span>](../../../../docs/framework/wcf/feature-details/security-guidance-and-best-practices.md)  
 [<span data-ttu-id="f1e96-153">Modelo de seguridad de Windows Server AppFabric</span><span class="sxs-lookup"><span data-stu-id="f1e96-153">Security Model for Windows Server App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
