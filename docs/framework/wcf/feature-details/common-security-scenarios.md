---
title: Escenarios de seguridad comunes
ms.date: 03/30/2017
helpviewer_keywords:
- security [WCF], scenarios
ms.assetid: 201923b5-5162-4a8a-8d4c-e7bd242748d5
ms.openlocfilehash: f36ebdb5ea248ec8134c688f89eb5d0be38dfe38
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84579741"
---
# <a name="common-security-scenarios"></a><span data-ttu-id="c73c0-102">Escenarios de seguridad comunes</span><span class="sxs-lookup"><span data-stu-id="c73c0-102">Common Security Scenarios</span></span>
<span data-ttu-id="c73c0-103">Los temas de esta sección catalogan varias configuraciones posibles de seguridad de cliente y servicio.</span><span class="sxs-lookup"><span data-stu-id="c73c0-103">The topics in this section catalog a number of possible client and service security configurations.</span></span> <span data-ttu-id="c73c0-104">Las configuraciones varían según varios factores.</span><span class="sxs-lookup"><span data-stu-id="c73c0-104">Configurations vary according to a number of factors.</span></span> <span data-ttu-id="c73c0-105">Por ejemplo, si un servicio o cliente está en una intranet o si Windows o transporte (como HTTPS) proporciona la seguridad.</span><span class="sxs-lookup"><span data-stu-id="c73c0-105">For example, whether a service or client is on an intranet, or whether the security is provided by Windows or transport (such as HTTPS).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c73c0-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="c73c0-106">In This Section</span></span>  
 [<span data-ttu-id="c73c0-107">Cliente y servicio de Internet no protegidos</span><span class="sxs-lookup"><span data-stu-id="c73c0-107">Internet Unsecured Client and Service</span></span>](internet-unsecured-client-and-service.md)  
 <span data-ttu-id="c73c0-108">Un ejemplo de un cliente y servicio público y no protegido.</span><span class="sxs-lookup"><span data-stu-id="c73c0-108">An example of a public, unsecured client and service.</span></span>  
  
 [<span data-ttu-id="c73c0-109">Cliente y servicio de intranet no protegidos</span><span class="sxs-lookup"><span data-stu-id="c73c0-109">Intranet Unsecured Client and Service</span></span>](intranet-unsecured-client-and-service.md)  
 <span data-ttu-id="c73c0-110">Un servicio básico de Windows Communication Foundation (WCF) desarrollado para proporcionar información sobre una red privada segura a una aplicación WCF.</span><span class="sxs-lookup"><span data-stu-id="c73c0-110">A basic Windows Communication Foundation (WCF) service developed to provide information on a secure private network to a WCF application.</span></span>  
  
 [<span data-ttu-id="c73c0-111">Seguridad de transporte con autenticación básica</span><span class="sxs-lookup"><span data-stu-id="c73c0-111">Transport Security with Basic Authentication</span></span>](transport-security-with-basic-authentication.md)  
 <span data-ttu-id="c73c0-112">La aplicación permite a los clientes iniciar sesión al utilizar autenticación personalizada.</span><span class="sxs-lookup"><span data-stu-id="c73c0-112">The application allows clients to log on using custom authentication.</span></span>  
  
 [<span data-ttu-id="c73c0-113">Seguridad del transporte con la autenticación de Windows</span><span class="sxs-lookup"><span data-stu-id="c73c0-113">Transport Security with Windows Authentication</span></span>](transport-security-with-windows-authentication.md)  
 <span data-ttu-id="c73c0-114">Muestra un cliente y servicio protegidos por seguridad de Windows.</span><span class="sxs-lookup"><span data-stu-id="c73c0-114">Shows a client and service secured by Windows security.</span></span>  
  
 [<span data-ttu-id="c73c0-115">Seguridad del transporte con clientes anónimos</span><span class="sxs-lookup"><span data-stu-id="c73c0-115">Transport Security with an Anonymous Client</span></span>](transport-security-with-an-anonymous-client.md)  
 <span data-ttu-id="c73c0-116">Este escenario utiliza la seguridad de transporte (como HTTPS) para garantizar la confidencialidad y la integridad.</span><span class="sxs-lookup"><span data-stu-id="c73c0-116">This scenario uses transport security (such as HTTPS) to ensure confidentiality and integrity.</span></span>  
  
 [<span data-ttu-id="c73c0-117">Seguridad del transporte con autenticación de certificados</span><span class="sxs-lookup"><span data-stu-id="c73c0-117">Transport Security with Certificate Authentication</span></span>](transport-security-with-certificate-authentication.md)  
 <span data-ttu-id="c73c0-118">Muestra a un cliente y servicio protegidos por un certificado.</span><span class="sxs-lookup"><span data-stu-id="c73c0-118">Shows a client and service secured by a certificate.</span></span>  
  
 [<span data-ttu-id="c73c0-119">Seguridad de mensajes con clientes anónimos</span><span class="sxs-lookup"><span data-stu-id="c73c0-119">Message Security with an Anonymous Client</span></span>](message-security-with-an-anonymous-client.md)  
 <span data-ttu-id="c73c0-120">Muestra un cliente y servicio protegido por la seguridad de mensajes de WCF.</span><span class="sxs-lookup"><span data-stu-id="c73c0-120">Shows a client and service secured by WCF message security.</span></span>  
  
 [<span data-ttu-id="c73c0-121">Seguridad de los mensajes con un cliente de nombres de usuario</span><span class="sxs-lookup"><span data-stu-id="c73c0-121">Message Security with a User Name Client</span></span>](message-security-with-a-user-name-client.md)  
 <span data-ttu-id="c73c0-122">El cliente es una aplicación de Windows Forms que permite a los clientes iniciar sesión al utilizar un nombre de usuario y contraseña del dominio.</span><span class="sxs-lookup"><span data-stu-id="c73c0-122">The client is a Windows Forms application that allows clients to log on using a domain user name and password.</span></span>  
  
 [<span data-ttu-id="c73c0-123">Seguridad de mensajes con un cliente de certificado</span><span class="sxs-lookup"><span data-stu-id="c73c0-123">Message Security with a Certificate Client</span></span>](message-security-with-a-certificate-client.md)  
 <span data-ttu-id="c73c0-124">Los servidores tienen certificados y cada cliente tiene un certificado.</span><span class="sxs-lookup"><span data-stu-id="c73c0-124">Servers have certificates, and each client has a certificate.</span></span> <span data-ttu-id="c73c0-125">Un contexto de seguridad se establece a través de la negociación de Seguridad de la capa de transporte (TLS).</span><span class="sxs-lookup"><span data-stu-id="c73c0-125">A security context is established through Transport Layer Security (TLS) negotiation.</span></span>  
  
 [<span data-ttu-id="c73c0-126">Seguridad del mensaje con un cliente de Windows</span><span class="sxs-lookup"><span data-stu-id="c73c0-126">Message Security with a Windows Client</span></span>](message-security-with-a-windows-client.md)  
 <span data-ttu-id="c73c0-127">Una variación del cliente del certificado.</span><span class="sxs-lookup"><span data-stu-id="c73c0-127">A variation of the certificate client.</span></span> <span data-ttu-id="c73c0-128">Los servidores tienen certificados y cada cliente tiene un certificado.</span><span class="sxs-lookup"><span data-stu-id="c73c0-128">Servers have certificates, and each client has a certificate.</span></span> <span data-ttu-id="c73c0-129">Un contexto de seguridad se establece a través de la negociación de TLS.</span><span class="sxs-lookup"><span data-stu-id="c73c0-129">A security context is established through TLS negotiation.</span></span>  
  
 [<span data-ttu-id="c73c0-130">Seguridad de los mensajes con un cliente de Windows sin negociación de credenciales</span><span class="sxs-lookup"><span data-stu-id="c73c0-130">Message Security with a Windows Client without Credential Negotiation</span></span>](message-security-with-a-windows-client-without-credential-negotiation.md)  
 <span data-ttu-id="c73c0-131">Muestra un cliente y el servicio protegidos por un dominio de Kerberos.</span><span class="sxs-lookup"><span data-stu-id="c73c0-131">Shows a client and service secured by a Kerberos domain.</span></span>  
  
 [<span data-ttu-id="c73c0-132">Seguridad de mensajes con certificados mutuos</span><span class="sxs-lookup"><span data-stu-id="c73c0-132">Message Security with Mutual Certificates</span></span>](message-security-with-mutual-certificates.md)  
 <span data-ttu-id="c73c0-133">Los servidores tienen certificados y cada cliente tiene un certificado.</span><span class="sxs-lookup"><span data-stu-id="c73c0-133">Servers have certificates, and each client has a certificate.</span></span> <span data-ttu-id="c73c0-134">El certificado de servidor se distribuye con la aplicación y está disponible fuera de banda.</span><span class="sxs-lookup"><span data-stu-id="c73c0-134">The server certificate is distributed with the application and is available out of band.</span></span>  
  
 [<span data-ttu-id="c73c0-135">Seguridad de los mensajes con tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="c73c0-135">Message Security with Issued Tokens</span></span>](message-security-with-issued-tokens.md)  
 <span data-ttu-id="c73c0-136">La seguridad federada que permite el establecimiento de confianza entre dominios independientes.</span><span class="sxs-lookup"><span data-stu-id="c73c0-136">Federated security that enables the establishment of trust between independent domains.</span></span>  
  
 [<span data-ttu-id="c73c0-137">Subsistema de confianza</span><span class="sxs-lookup"><span data-stu-id="c73c0-137">Trusted Subsystem</span></span>](trusted-subsystem.md)  
 <span data-ttu-id="c73c0-138">Un cliente obtiene acceso a uno o varios servicios Web distribuidos a través de una red.</span><span class="sxs-lookup"><span data-stu-id="c73c0-138">A client accesses one or more Web services that are distributed across a network.</span></span> <span data-ttu-id="c73c0-139">Los servicios Web tienen acceso a recursos adicionales (como bases de datos u otros servicios Web) que se deben proteger.</span><span class="sxs-lookup"><span data-stu-id="c73c0-139">The Web services access additional resources (such as databases or other Web services) that must be secured.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="c73c0-140">Referencia</span><span class="sxs-lookup"><span data-stu-id="c73c0-140">Reference</span></span>  
 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a><span data-ttu-id="c73c0-141">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="c73c0-141">Related Sections</span></span>  
 [<span data-ttu-id="c73c0-142">Autorización</span><span class="sxs-lookup"><span data-stu-id="c73c0-142">Authorization</span></span>](authorization-in-wcf.md)  
  
 [<span data-ttu-id="c73c0-143">Información general sobre seguridad</span><span class="sxs-lookup"><span data-stu-id="c73c0-143">Security Overview</span></span>](security-overview.md)  
  
 [<span data-ttu-id="c73c0-144">Seguridad</span><span class="sxs-lookup"><span data-stu-id="c73c0-144">Security</span></span>](security.md)  
  
 [<span data-ttu-id="c73c0-145">Enlaces y seguridad</span><span class="sxs-lookup"><span data-stu-id="c73c0-145">Bindings and Security</span></span>](bindings-and-security.md)  
  
 [<span data-ttu-id="c73c0-146">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="c73c0-146">Securing Services and Clients</span></span>](securing-services-and-clients.md)  
  
 [<span data-ttu-id="c73c0-147">Autenticación</span><span class="sxs-lookup"><span data-stu-id="c73c0-147">Authentication</span></span>](authentication-in-wcf.md)  
  
 [<span data-ttu-id="c73c0-148">Autorización</span><span class="sxs-lookup"><span data-stu-id="c73c0-148">Authorization</span></span>](authorization-in-wcf.md)  
  
 [<span data-ttu-id="c73c0-149">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="c73c0-149">Federation and Issued Tokens</span></span>](federation-and-issued-tokens.md)  
  
 [<span data-ttu-id="c73c0-150">Auditoría</span><span class="sxs-lookup"><span data-stu-id="c73c0-150">Auditing</span></span>](auditing-security-events.md)  
  
## <a name="see-also"></a><span data-ttu-id="c73c0-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="c73c0-151">See also</span></span>

- [<span data-ttu-id="c73c0-152">Orientación de seguridad y procedimientos recomendados</span><span class="sxs-lookup"><span data-stu-id="c73c0-152">Security Guidance and Best Practices</span></span>](security-guidance-and-best-practices.md)
- <span data-ttu-id="c73c0-153">[Modelo de seguridad para Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="c73c0-153">[Security Model for Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
