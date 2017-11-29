---
title: "Protocolos de seguridad versión 1.0"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ee3402d2-1076-410b-a3cb-fae0372bd7af
caps.latest.revision: "4"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: f40c79ad1a6eedc2b1de4dffa9de5b48aeb8e6f5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="security-protocols-version-10"></a><span data-ttu-id="2b4e0-102">Protocolos de seguridad versión 1.0</span><span class="sxs-lookup"><span data-stu-id="2b4e0-102">Security Protocols version 1.0</span></span>
<span data-ttu-id="2b4e0-103">Los protocolos de seguridad de servicios Web proporcionan mecanismos de seguridad de servicios Web que cubren todos los requisitos de seguridad de mensajería para empresas existentes.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-103">The Web Services Security Protocols provide Web services security mechanisms that cover all existing enterprise messaging security requirements.</span></span> <span data-ttu-id="2b4e0-104">En esta sección se describen los detalles de la versión 1.0 de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] (implementados en el <xref:System.ServiceModel.Channels.SecurityBindingElement>) para los siguientes protocolos de seguridad de servicios Web.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-104">This section describes the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] version 1.0 details (implemented in the <xref:System.ServiceModel.Channels.SecurityBindingElement>) for the following Web services security protocols.</span></span>  
  
|<span data-ttu-id="2b4e0-105">Especificación/documento</span><span class="sxs-lookup"><span data-stu-id="2b4e0-105">Specification/Document</span></span>|<span data-ttu-id="2b4e0-106">Link</span><span class="sxs-lookup"><span data-stu-id="2b4e0-106">Link</span></span>|  
|-|-|  
|<span data-ttu-id="2b4e0-107">WSS: Message Security 1,0 de SOAP</span><span class="sxs-lookup"><span data-stu-id="2b4e0-107">WSS: SOAP Message Security 1.0</span></span>|<span data-ttu-id="2b4e0-108">http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-soap-message-security-1.0.pdf</span><span class="sxs-lookup"><span data-stu-id="2b4e0-108">http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-soap-message-security-1.0.pdf</span></span>|  
|<span data-ttu-id="2b4e0-109">WSS: Token Profile 1.0 de Username</span><span class="sxs-lookup"><span data-stu-id="2b4e0-109">WSS: Username Token Profile 1.0</span></span>|<span data-ttu-id="2b4e0-110">http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-username-token-profile-1.0.pdf</span><span class="sxs-lookup"><span data-stu-id="2b4e0-110">http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-username-token-profile-1.0.pdf</span></span>|  
|<span data-ttu-id="2b4e0-111">WSS: Token Profile 1,0 de X509</span><span class="sxs-lookup"><span data-stu-id="2b4e0-111">WSS: X509 Token Profile 1.0</span></span>|<span data-ttu-id="2b4e0-112">http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-x509-token-profile-1.0.pdf</span><span class="sxs-lookup"><span data-stu-id="2b4e0-112">http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-x509-token-profile-1.0.pdf</span></span>|  
|<span data-ttu-id="2b4e0-113">WSS: Token Profile 1.1 de SAML 1,0</span><span class="sxs-lookup"><span data-stu-id="2b4e0-113">WSS: SAML 1.1 Token Profile 1.0</span></span>|<span data-ttu-id="2b4e0-114">http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.0.pdf</span><span class="sxs-lookup"><span data-stu-id="2b4e0-114">http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.0.pdf</span></span>|  
|<span data-ttu-id="2b4e0-115">WSS: Message Security 1.1 de SOAP</span><span class="sxs-lookup"><span data-stu-id="2b4e0-115">WSS: SOAP Message Security 1.1</span></span>|<span data-ttu-id="2b4e0-116">http://www.oasis-open.org/committees/download.php/16790/wss-v1.1-spec-os-SOAPMessageSecurity.pdf</span><span class="sxs-lookup"><span data-stu-id="2b4e0-116">http://www.oasis-open.org/committees/download.php/16790/wss-v1.1-spec-os-SOAPMessageSecurity.pdf</span></span>|  
|<span data-ttu-id="2b4e0-117">WSS: Token Profile 1.1 de Username</span><span class="sxs-lookup"><span data-stu-id="2b4e0-117">WSS Username Token Profile 1.1</span></span>|<span data-ttu-id="2b4e0-118">http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-username-token-profile-1.0.pdf</span><span class="sxs-lookup"><span data-stu-id="2b4e0-118">http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-username-token-profile-1.0.pdf</span></span>|  
|<span data-ttu-id="2b4e0-119">WSS: Token Profile 1,1 de X.509</span><span class="sxs-lookup"><span data-stu-id="2b4e0-119">WSS: X.509 Token Profile 1.1</span></span>|<span data-ttu-id="2b4e0-120">http://www.oasis-open.org/committees/download.php/16785/wss-v1.1-spec-os-x509TokenProfile.pdf</span><span class="sxs-lookup"><span data-stu-id="2b4e0-120">http://www.oasis-open.org/committees/download.php/16785/wss-v1.1-spec-os-x509TokenProfile.pdf</span></span>|  
|<span data-ttu-id="2b4e0-121">WSS: Token Profile 1.1 de Kerberos</span><span class="sxs-lookup"><span data-stu-id="2b4e0-121">WSS: Kerberos Token Profile 1.1</span></span>|<span data-ttu-id="2b4e0-122">http://www.oasis-open.org/committees/download.php/16788/wss-v1.1-spec-os-KerberosTokenProfile.pdf</span><span class="sxs-lookup"><span data-stu-id="2b4e0-122">http://www.oasis-open.org/committees/download.php/16788/wss-v1.1-spec-os-KerberosTokenProfile.pdf</span></span>|  
|<span data-ttu-id="2b4e0-123">WSS: Token Profile 1.1 de SAML 1.1</span><span class="sxs-lookup"><span data-stu-id="2b4e0-123">WSS: SAML 1.1 Token Profile 1.1</span></span>|<span data-ttu-id="2b4e0-124">http://www.oasis-open.org/committees/download.php/16768/wss-v1.1-spec-os-SAMLTokenProfile.pdf</span><span class="sxs-lookup"><span data-stu-id="2b4e0-124">http://www.oasis-open.org/committees/download.php/16768/wss-v1.1-spec-os-SAMLTokenProfile.pdf</span></span>|  
|<span data-ttu-id="2b4e0-125">WS-Secure Conversation</span><span class="sxs-lookup"><span data-stu-id="2b4e0-125">WS-Secure Conversation</span></span>|<span data-ttu-id="2b4e0-126">http://msdn.microsoft.com/ws/2005/02/ws-secure-conversation/</span><span class="sxs-lookup"><span data-stu-id="2b4e0-126">http://msdn.microsoft.com/ws/2005/02/ws-secure-conversation/</span></span>|  
|<span data-ttu-id="2b4e0-127">WS-Trust</span><span class="sxs-lookup"><span data-stu-id="2b4e0-127">WS-Trust</span></span>|<span data-ttu-id="2b4e0-128">http://msdn.microsoft.com/ws/2005/02/ws-trust/</span><span class="sxs-lookup"><span data-stu-id="2b4e0-128">http://msdn.microsoft.com/ws/2005/02/ws-trust/</span></span>|  
|<span data-ttu-id="2b4e0-129">Nota de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="2b4e0-129">Application Note:</span></span><br /><br /> <span data-ttu-id="2b4e0-130">Uso de WS-Trust para protocolo de enlace TLS</span><span class="sxs-lookup"><span data-stu-id="2b4e0-130">Using WS-Trust for TLS Handshake</span></span>|<span data-ttu-id="2b4e0-131">Para su publicación</span><span class="sxs-lookup"><span data-stu-id="2b4e0-131">To be published</span></span>|  
|<span data-ttu-id="2b4e0-132">Nota de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="2b4e0-132">Application Note:</span></span><br /><br /> <span data-ttu-id="2b4e0-133">Uso de WS-Trust para SPNEGO</span><span class="sxs-lookup"><span data-stu-id="2b4e0-133">Using WS-Trust for SPNEGO</span></span>|<span data-ttu-id="2b4e0-134">Para su publicación</span><span class="sxs-lookup"><span data-stu-id="2b4e0-134">To be published</span></span>|  
|<span data-ttu-id="2b4e0-135">Nota de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="2b4e0-135">Application Note:</span></span><br /><br /> <span data-ttu-id="2b4e0-136">Referencias e identidad de extremos de direccionamiento de servicios Web</span><span class="sxs-lookup"><span data-stu-id="2b4e0-136">Web Services Addressing Endpoint References And Identity</span></span>|<span data-ttu-id="2b4e0-137">Para su publicación</span><span class="sxs-lookup"><span data-stu-id="2b4e0-137">To be published</span></span>|  
|<span data-ttu-id="2b4e0-138">WS-SecurityPolicy 1.1</span><span class="sxs-lookup"><span data-stu-id="2b4e0-138">WS-SecurityPolicy 1.1</span></span><br /><br /> <span data-ttu-id="2b4e0-139">(2005/07)</span><span class="sxs-lookup"><span data-stu-id="2b4e0-139">(2005/07)</span></span>|<span data-ttu-id="2b4e0-140">http://msdn.microsoft.com/ws/2005/07/ws-security-policy/</span><span class="sxs-lookup"><span data-stu-id="2b4e0-140">http://msdn.microsoft.com/ws/2005/07/ws-security-policy/</span></span><br /><br /> <span data-ttu-id="2b4e0-141">tal y como se corrigió gracias a las erratas enviadas al comité técnico de WS-SX OASIS http://www.oasis-open.org/archives/ws-sx/200512/msg00017.html</span><span class="sxs-lookup"><span data-stu-id="2b4e0-141">as amended by errata submitted to OASIS WS-SX Technical Committee http://www.oasis-open.org/archives/ws-sx/200512/msg00017.html</span></span>|  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="2b4e0-142">, versión 1, proporciona 17 modos de autenticación que se pueden utilizar como base para la configuración de seguridad de servicios Web.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-142">, version 1, provides 17 authentication modes that can be used as the basis for Web services security configuration.</span></span> <span data-ttu-id="2b4e0-143">Cada modo se optimiza para un conjunto común de requisitos de implementación, como:</span><span class="sxs-lookup"><span data-stu-id="2b4e0-143">Each mode is optimized for a common set of deployment requirements, such as:</span></span>  
  
-   <span data-ttu-id="2b4e0-144">Credenciales utilizadas para autenticar cliente y servicio.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-144">Credentials used to authenticate client and service.</span></span>  
  
-   <span data-ttu-id="2b4e0-145">Mecanismos de protección de seguridad de transporte o mensaje.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-145">Message or transport security protection mechanisms.</span></span>  
  
-   <span data-ttu-id="2b4e0-146">Patrones de intercambio de mensajes.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-146">Message exchange patterns.</span></span>  
  
|<span data-ttu-id="2b4e0-147">Modo de autenticación</span><span class="sxs-lookup"><span data-stu-id="2b4e0-147">Authentication Mode</span></span>|<span data-ttu-id="2b4e0-148">Autenticación del cliente</span><span class="sxs-lookup"><span data-stu-id="2b4e0-148">Client Authentication</span></span>|<span data-ttu-id="2b4e0-149">Autenticación de servidor</span><span class="sxs-lookup"><span data-stu-id="2b4e0-149">Server Authentication</span></span>|<span data-ttu-id="2b4e0-150">Modo</span><span class="sxs-lookup"><span data-stu-id="2b4e0-150">Mode</span></span>|  
|-------------------------|---------------------------|---------------------------|----------|  
|<span data-ttu-id="2b4e0-151">UserNameOverTransport</span><span class="sxs-lookup"><span data-stu-id="2b4e0-151">UserNameOverTransport</span></span>|<span data-ttu-id="2b4e0-152">Nombre de usuario/contraseña</span><span class="sxs-lookup"><span data-stu-id="2b4e0-152">User name/password</span></span>|<span data-ttu-id="2b4e0-153">X509</span><span class="sxs-lookup"><span data-stu-id="2b4e0-153">X509</span></span>|<span data-ttu-id="2b4e0-154">Transporte</span><span class="sxs-lookup"><span data-stu-id="2b4e0-154">Transport</span></span>|  
|<span data-ttu-id="2b4e0-155">CertificateOverTransport</span><span class="sxs-lookup"><span data-stu-id="2b4e0-155">CertificateOverTransport</span></span>|<span data-ttu-id="2b4e0-156">X509</span><span class="sxs-lookup"><span data-stu-id="2b4e0-156">X509</span></span>|<span data-ttu-id="2b4e0-157">X509</span><span class="sxs-lookup"><span data-stu-id="2b4e0-157">X509</span></span>|<span data-ttu-id="2b4e0-158">Transporte</span><span class="sxs-lookup"><span data-stu-id="2b4e0-158">Transport</span></span>|  
|<span data-ttu-id="2b4e0-159">KerberosOverTransport</span><span class="sxs-lookup"><span data-stu-id="2b4e0-159">KerberosOverTransport</span></span>|<span data-ttu-id="2b4e0-160">Windows</span><span class="sxs-lookup"><span data-stu-id="2b4e0-160">Windows</span></span>|<span data-ttu-id="2b4e0-161">X509</span><span class="sxs-lookup"><span data-stu-id="2b4e0-161">X509</span></span>|<span data-ttu-id="2b4e0-162">Transporte</span><span class="sxs-lookup"><span data-stu-id="2b4e0-162">Transport</span></span>|  
|<span data-ttu-id="2b4e0-163">IssuedTokenOverTransport</span><span class="sxs-lookup"><span data-stu-id="2b4e0-163">IssuedTokenOverTransport</span></span>|<span data-ttu-id="2b4e0-164">Federado</span><span class="sxs-lookup"><span data-stu-id="2b4e0-164">Federated</span></span>|<span data-ttu-id="2b4e0-165">X509</span><span class="sxs-lookup"><span data-stu-id="2b4e0-165">X509</span></span>|<span data-ttu-id="2b4e0-166">Transporte</span><span class="sxs-lookup"><span data-stu-id="2b4e0-166">Transport</span></span>|  
|<span data-ttu-id="2b4e0-167">SspiNegotiatedOverTransport</span><span class="sxs-lookup"><span data-stu-id="2b4e0-167">SspiNegotiatedOverTransport</span></span>|<span data-ttu-id="2b4e0-168">Windows SSPI negociado</span><span class="sxs-lookup"><span data-stu-id="2b4e0-168">Windows Sspi Negotiated</span></span>|<span data-ttu-id="2b4e0-169">Windows SSPI negociado</span><span class="sxs-lookup"><span data-stu-id="2b4e0-169">Windows Sspi Negotiated</span></span>|<span data-ttu-id="2b4e0-170">Transporte</span><span class="sxs-lookup"><span data-stu-id="2b4e0-170">Transport</span></span>|  
|<span data-ttu-id="2b4e0-171">AnonymousForCertificate</span><span class="sxs-lookup"><span data-stu-id="2b4e0-171">AnonymousForCertificate</span></span>|<span data-ttu-id="2b4e0-172">Ninguna</span><span class="sxs-lookup"><span data-stu-id="2b4e0-172">None</span></span>|<span data-ttu-id="2b4e0-173">X509</span><span class="sxs-lookup"><span data-stu-id="2b4e0-173">X509</span></span>|<span data-ttu-id="2b4e0-174">Mensaje</span><span class="sxs-lookup"><span data-stu-id="2b4e0-174">Message</span></span>|  
|<span data-ttu-id="2b4e0-175">UserNameForCertificate</span><span class="sxs-lookup"><span data-stu-id="2b4e0-175">UserNameForCertificate</span></span>|<span data-ttu-id="2b4e0-176">Nombre de usuario/contraseña</span><span class="sxs-lookup"><span data-stu-id="2b4e0-176">User name/password</span></span>|<span data-ttu-id="2b4e0-177">X509</span><span class="sxs-lookup"><span data-stu-id="2b4e0-177">X509</span></span>|<span data-ttu-id="2b4e0-178">Mensaje</span><span class="sxs-lookup"><span data-stu-id="2b4e0-178">Message</span></span>|  
|<span data-ttu-id="2b4e0-179">MutualCertificate</span><span class="sxs-lookup"><span data-stu-id="2b4e0-179">MutualCertificate</span></span>|<span data-ttu-id="2b4e0-180">X509</span><span class="sxs-lookup"><span data-stu-id="2b4e0-180">X509</span></span>|<span data-ttu-id="2b4e0-181">X509</span><span class="sxs-lookup"><span data-stu-id="2b4e0-181">X509</span></span>|<span data-ttu-id="2b4e0-182">Mensaje</span><span class="sxs-lookup"><span data-stu-id="2b4e0-182">Message</span></span>|  
|<span data-ttu-id="2b4e0-183">MutualCertificateDuplex</span><span class="sxs-lookup"><span data-stu-id="2b4e0-183">MutualCertificateDuplex</span></span>|<span data-ttu-id="2b4e0-184">X509</span><span class="sxs-lookup"><span data-stu-id="2b4e0-184">X509</span></span>|<span data-ttu-id="2b4e0-185">X509</span><span class="sxs-lookup"><span data-stu-id="2b4e0-185">X509</span></span>|<span data-ttu-id="2b4e0-186">Mensaje</span><span class="sxs-lookup"><span data-stu-id="2b4e0-186">Message</span></span>|  
|<span data-ttu-id="2b4e0-187">IssuedTokenForCertificate</span><span class="sxs-lookup"><span data-stu-id="2b4e0-187">IssuedTokenForCertificate</span></span>|<span data-ttu-id="2b4e0-188">Federado</span><span class="sxs-lookup"><span data-stu-id="2b4e0-188">Federated</span></span>|<span data-ttu-id="2b4e0-189">X509</span><span class="sxs-lookup"><span data-stu-id="2b4e0-189">X509</span></span>|<span data-ttu-id="2b4e0-190">Mensaje</span><span class="sxs-lookup"><span data-stu-id="2b4e0-190">Message</span></span>|  
|<span data-ttu-id="2b4e0-191">Kerberos</span><span class="sxs-lookup"><span data-stu-id="2b4e0-191">Kerberos</span></span>|<span data-ttu-id="2b4e0-192">Windows</span><span class="sxs-lookup"><span data-stu-id="2b4e0-192">Windows</span></span>|<span data-ttu-id="2b4e0-193">Windows</span><span class="sxs-lookup"><span data-stu-id="2b4e0-193">Windows</span></span>|<span data-ttu-id="2b4e0-194">Mensaje</span><span class="sxs-lookup"><span data-stu-id="2b4e0-194">Message</span></span>|  
|<span data-ttu-id="2b4e0-195">IssuedToken</span><span class="sxs-lookup"><span data-stu-id="2b4e0-195">IssuedToken</span></span>|<span data-ttu-id="2b4e0-196">Federado</span><span class="sxs-lookup"><span data-stu-id="2b4e0-196">Federated</span></span>|<span data-ttu-id="2b4e0-197">Federado</span><span class="sxs-lookup"><span data-stu-id="2b4e0-197">Federated</span></span>|<span data-ttu-id="2b4e0-198">Mensaje</span><span class="sxs-lookup"><span data-stu-id="2b4e0-198">Message</span></span>|  
|<span data-ttu-id="2b4e0-199">SspiNegotiated</span><span class="sxs-lookup"><span data-stu-id="2b4e0-199">SspiNegotiated</span></span>|<span data-ttu-id="2b4e0-200">Windows SSPI negociado</span><span class="sxs-lookup"><span data-stu-id="2b4e0-200">Windows Sspi Negotiated</span></span>|<span data-ttu-id="2b4e0-201">Windows SSPI negociado</span><span class="sxs-lookup"><span data-stu-id="2b4e0-201">Windows Sspi Negotiated</span></span>|<span data-ttu-id="2b4e0-202">Mensaje</span><span class="sxs-lookup"><span data-stu-id="2b4e0-202">Message</span></span>|  
|<span data-ttu-id="2b4e0-203">AnonymousForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="2b4e0-203">AnonymousForSslNegotiated</span></span>|<span data-ttu-id="2b4e0-204">Ninguna</span><span class="sxs-lookup"><span data-stu-id="2b4e0-204">None</span></span>|<span data-ttu-id="2b4e0-205">X509, TLS-Nego</span><span class="sxs-lookup"><span data-stu-id="2b4e0-205">X509, TLS-Nego</span></span>|<span data-ttu-id="2b4e0-206">Mensaje</span><span class="sxs-lookup"><span data-stu-id="2b4e0-206">Message</span></span>|  
|<span data-ttu-id="2b4e0-207">UserNameForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="2b4e0-207">UserNameForSslNegotiated</span></span>|<span data-ttu-id="2b4e0-208">Nombre de usuario/contraseña</span><span class="sxs-lookup"><span data-stu-id="2b4e0-208">User name/password</span></span>|<span data-ttu-id="2b4e0-209">X509, TLS-Nego</span><span class="sxs-lookup"><span data-stu-id="2b4e0-209">X509, TLS-Nego</span></span>|<span data-ttu-id="2b4e0-210">Mensaje</span><span class="sxs-lookup"><span data-stu-id="2b4e0-210">Message</span></span>|  
|<span data-ttu-id="2b4e0-211">MutualSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="2b4e0-211">MutualSslNegotiated</span></span>|<span data-ttu-id="2b4e0-212">X509</span><span class="sxs-lookup"><span data-stu-id="2b4e0-212">X509</span></span>|<span data-ttu-id="2b4e0-213">X509, TLS-Nego</span><span class="sxs-lookup"><span data-stu-id="2b4e0-213">X509, TLS-Nego</span></span>|<span data-ttu-id="2b4e0-214">Mensaje</span><span class="sxs-lookup"><span data-stu-id="2b4e0-214">Message</span></span>|  
|<span data-ttu-id="2b4e0-215">IssuedTokenForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="2b4e0-215">IssuedTokenForSslNegotiated</span></span>|<span data-ttu-id="2b4e0-216">Federado</span><span class="sxs-lookup"><span data-stu-id="2b4e0-216">Federated</span></span>|<span data-ttu-id="2b4e0-217">X509, TLS-Nego</span><span class="sxs-lookup"><span data-stu-id="2b4e0-217">X509, TLS-Nego</span></span>|<span data-ttu-id="2b4e0-218">Mensaje</span><span class="sxs-lookup"><span data-stu-id="2b4e0-218">Message</span></span>|  
  
 <span data-ttu-id="2b4e0-219">Los extremos que usan tales modos de autenticación pueden expresar sus requisitos de seguridad mediante WS-SecurityPolicy (WS-SP).</span><span class="sxs-lookup"><span data-stu-id="2b4e0-219">Endpoints using such authentication modes can express their security requirements using WS-SecurityPolicy (WS-SP).</span></span> <span data-ttu-id="2b4e0-220">Este documento describe la estructura de mensajes de infraestructura y encabezado de seguridad para cada modo de autenticación y proporciona ejemplos de directivas y mensajes.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-220">This document describes the structure of security header and infrastructure messages for each authentication mode and provides examples of policies and messages.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="2b4e0-221"> reutiliza WS-SecureConversation para proporcionar compatibilidad con sesiones seguras para proteger los intercambios de múltiples mensaje entre aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-221"> leverages WS-SecureConversation to provide secure sessions support to protect multi-message exchanges between applications.</span></span>  <span data-ttu-id="2b4e0-222">Vea "Sesiones seguras" más abajo para obtener detalles de implementación.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-222">See "Secure Sessions" below for implementation details.</span></span>  
  
 <span data-ttu-id="2b4e0-223">Además de los modos de autenticación, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] proporciona ajustes para controlar mecanismos de protección comunes que se aplican a la mayoría de modos de autenticación basados en seguridad, como, por ejemplo: orden de firma frente a operaciones de cifrado, conjuntos de algoritmos, derivación de claves y confirmación de firmas.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-223">In addition to authentication modes, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] provides settings to control common protection mechanisms that apply to most message security-based authentication modes, for example: order of signature versus encryption operations, algorithm suites, key derivation, and signature confirmation.</span></span>  
  
 <span data-ttu-id="2b4e0-224">Los siguientes prefijos y espacios de nombres se utilizan en este documento.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-224">The following prefixes and namespaces are used in this document.</span></span>  
  
|<span data-ttu-id="2b4e0-225">Prefijo</span><span class="sxs-lookup"><span data-stu-id="2b4e0-225">Prefix</span></span>|<span data-ttu-id="2b4e0-226">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="2b4e0-226">Namespace</span></span>|  
|------------|---------------|  
|<span data-ttu-id="2b4e0-227">s</span><span class="sxs-lookup"><span data-stu-id="2b4e0-227">s</span></span>|<span data-ttu-id="2b4e0-228">http://www.w3.org/2003/05/soap-envelope</span><span class="sxs-lookup"><span data-stu-id="2b4e0-228">http://www.w3.org/2003/05/soap-envelope</span></span>|  
|<span data-ttu-id="2b4e0-229">sp</span><span class="sxs-lookup"><span data-stu-id="2b4e0-229">sp</span></span>|<span data-ttu-id="2b4e0-230">http://schemas.xmlsoap.org/ws/2005/07/securitypolicy</span><span class="sxs-lookup"><span data-stu-id="2b4e0-230">http://schemas.xmlsoap.org/ws/2005/07/securitypolicy</span></span>|  
|<span data-ttu-id="2b4e0-231">a</span><span class="sxs-lookup"><span data-stu-id="2b4e0-231">a</span></span>|<span data-ttu-id="2b4e0-232">http://www.w3.org/2005/08/addressing</span><span class="sxs-lookup"><span data-stu-id="2b4e0-232">http://www.w3.org/2005/08/addressing</span></span>|  
|<span data-ttu-id="2b4e0-233">wsse</span><span class="sxs-lookup"><span data-stu-id="2b4e0-233">wsse</span></span>|<span data-ttu-id="2b4e0-234">TBD – OASIS WSS 1,0 URI</span><span class="sxs-lookup"><span data-stu-id="2b4e0-234">TBD – OASIS WSS 1.0 URI</span></span>|  
|<span data-ttu-id="2b4e0-235">wsse11</span><span class="sxs-lookup"><span data-stu-id="2b4e0-235">wsse11</span></span>|<span data-ttu-id="2b4e0-236">TBD – OASIS WSS 1.1 URI</span><span class="sxs-lookup"><span data-stu-id="2b4e0-236">TBD – OASIS WSS 1.1 URI</span></span>|  
|<span data-ttu-id="2b4e0-237">wsu</span><span class="sxs-lookup"><span data-stu-id="2b4e0-237">wsu</span></span>|<span data-ttu-id="2b4e0-238">TBD – OASIS WSS 1.0 Utility URI</span><span class="sxs-lookup"><span data-stu-id="2b4e0-238">TBD – OASIS WSS 1.0 Utility URI</span></span>|  
|<span data-ttu-id="2b4e0-239">ds</span><span class="sxs-lookup"><span data-stu-id="2b4e0-239">ds</span></span>|<span data-ttu-id="2b4e0-240">TBD – W3C XMLDSig URI</span><span class="sxs-lookup"><span data-stu-id="2b4e0-240">TBD – W3C XMLDSig URI</span></span>|  
|<span data-ttu-id="2b4e0-241">wst</span><span class="sxs-lookup"><span data-stu-id="2b4e0-241">wst</span></span>|<span data-ttu-id="2b4e0-242">TBD – WS-Trust 2005/02 URI</span><span class="sxs-lookup"><span data-stu-id="2b4e0-242">TBD – WS-Trust 2005/02 URI</span></span>|  
|<span data-ttu-id="2b4e0-243">wssc</span><span class="sxs-lookup"><span data-stu-id="2b4e0-243">wssc</span></span>|<span data-ttu-id="2b4e0-244">TBD – WS-SecureConversation 2005/02 URI</span><span class="sxs-lookup"><span data-stu-id="2b4e0-244">TBD – WS-SecureConversation 2005/02 URI</span></span>|  
|<span data-ttu-id="2b4e0-245">wsaw</span><span class="sxs-lookup"><span data-stu-id="2b4e0-245">wsaw</span></span>|<span data-ttu-id="2b4e0-246">TBD - Espacio de nombres de directiva WS-Addressing</span><span class="sxs-lookup"><span data-stu-id="2b4e0-246">TBD - WS-Addressing policy namespace</span></span>|  
|<span data-ttu-id="2b4e0-247">wsp</span><span class="sxs-lookup"><span data-stu-id="2b4e0-247">wsp</span></span>|<span data-ttu-id="2b4e0-248">http://schemas.xmlsoap.org/ws/2004/09/policy</span><span class="sxs-lookup"><span data-stu-id="2b4e0-248">http://schemas.xmlsoap.org/ws/2004/09/policy</span></span>|  
|<span data-ttu-id="2b4e0-249">mssp</span><span class="sxs-lookup"><span data-stu-id="2b4e0-249">mssp</span></span>|<span data-ttu-id="2b4e0-250">http://schemas.microsoft.com/ws/2005/07/securitypolicy</span><span class="sxs-lookup"><span data-stu-id="2b4e0-250">http://schemas.microsoft.com/ws/2005/07/securitypolicy</span></span>|  
  
## <a name="1-token-profiles"></a><span data-ttu-id="2b4e0-251">1. Perfiles de tokens</span><span class="sxs-lookup"><span data-stu-id="2b4e0-251">1. Token Profiles</span></span>  
 <span data-ttu-id="2b4e0-252">Las especificaciones Seguridad de Servicios web representan la credencial como tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-252">Web Services Security specifications represent credential as security tokens.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="2b4e0-253"> admite los siguientes tipos de token:</span><span class="sxs-lookup"><span data-stu-id="2b4e0-253"> supports the following token types:</span></span>  
  
### <a name="11-usernametoken"></a><span data-ttu-id="2b4e0-254">1.1 UsernameToken</span><span class="sxs-lookup"><span data-stu-id="2b4e0-254">1.1 UsernameToken</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="2b4e0-255"> sigue perfiles UsernameToken10 y UsernameToken11 con las restricciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="2b4e0-255"> follows UsernameToken10 and UsernameToken11 profiles with the following constraints:</span></span>  
  
 <span data-ttu-id="2b4e0-256">El atributo R1101 PasswordType en el elemento UsernameToken\Password no se debe omitir ni debe tener el valor #PasswordText (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="2b4e0-256">R1101 PasswordType attribute on UsernameToken\Password element MUST be either omitted or have value #PasswordText (default).</span></span>  
  
 <span data-ttu-id="2b4e0-257">Uno puede implementar el #PasswordDigest mediante extensibilidad.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-257">One can implement the #PasswordDigest using extensibility.</span></span> <span data-ttu-id="2b4e0-258">Se ha observado que #PasswordDigest se confunde a menudo como un mecanismo de protección de contraseña suficientemente seguro.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-258">It has been observed that #PasswordDigest was often mistaken to be a secure enough password protection mechanism.</span></span> <span data-ttu-id="2b4e0-259">Pero #PasswordDigest no puede actuar como un sustituto del cifrado del UsernameToken.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-259">But #PasswordDigest cannot serve as a substitute for encryption of the UsernameToken.</span></span> <span data-ttu-id="2b4e0-260">El objetivo principal de #PasswordDigest es la protección frente a ataques mediante repetición.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-260">The primary goal of #PasswordDigest is protection against replay attacks.</span></span> <span data-ttu-id="2b4e0-261">En los modos de autenticación de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], las amenazas de ataques mediante repetición se mitigan mediante las firmas de mensaje.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-261">In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] authentication modes, replay attack threats are mitigated by using message signatures.</span></span>  
  
 <span data-ttu-id="2b4e0-262">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] de B1102 nunca emite subelementos Nonce y Created del UsernameToken.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-262">B1102 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] never emits Nonce and Created sub-elements of the UsernameToken.</span></span>  
  
 <span data-ttu-id="2b4e0-263">Estos subelementos están diseñados para ayudar a detectar las repeticiones.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-263">These sub-elements are intended to help replay detection.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="2b4e0-264"> usa signaturas de mensaje en su lugar.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-264"> uses message signatures instead.</span></span>  
  
 <span data-ttu-id="2b4e0-265">Perfil 1.1 de UsernameToken de seguridad de mensajes SOAP WSS OASIS (UsernameToken11) introdujo la característica de derivación de claves a partir de la contraseña.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-265">OASIS WSS SOAP Message Security UsernameToken Profile 1.1 (UsernameToken11) introduced key derivation from password feature.</span></span>  
  
 <span data-ttu-id="2b4e0-266">La contraseña de UsernameToken B1103 no se debe utilizar para la derivación de claves ni, por consiguiente, para las operaciones criptográficas.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-266">B1103 UsernameToken password MUST not be used for key derivation and therefore for cryptographic operations.</span></span>  
  
 <span data-ttu-id="2b4e0-267">Razón: las contraseñas generalmente están consideradas demasiado débiles como para ser utilizadas para operaciones criptográficas.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-267">Rationale: passwords are generally considered too weak to be used for cryptographic operations.</span></span>  
  
### <a name="12-x509-token"></a><span data-ttu-id="2b4e0-268">1.2 Token X509</span><span class="sxs-lookup"><span data-stu-id="2b4e0-268">1.2 X509 Token</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="2b4e0-269"> admite certificados X509v3 como un tipo de credencial y sigue X509TokenProfile1.0 y X509TokenProfile1.1 con las siguientes restricciones:</span><span class="sxs-lookup"><span data-stu-id="2b4e0-269"> supports X509v3 certificates as a credential type and follows X509TokenProfile1.0 and X509TokenProfile1.1 with the following constraints:</span></span>  
  
 <span data-ttu-id="2b4e0-270">R1201 El atributo ValueType en el elemento BinarySecurityToken debe tener el valor #X509v3 cuando contiene un certificado X509v3.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-270">R1201 The ValueType attribute on the BinarySecurityToken element must have value #X509v3 when it contains an X509v3 certificate.</span></span>  
  
 <span data-ttu-id="2b4e0-271">Los perfiles 1.0 y 1.1 de token de WSS X509 también definen #X509PKIPathv1 y #PKCS7 como tipos de valor.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-271">WSS X509 Token Profile 1.0 and 1.1 define also #X509PKIPathv1 and #PKCS7 as value types.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="2b4e0-272"> no admite estos tipos.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-272"> does not support these types.</span></span>  
  
 <span data-ttu-id="2b4e0-273">R1202 Si una extensión SubjectKeyIdentifier (SKI) se encuentra en un certificado X509, se debería utilizar wsse:KeyIdentifier para las referencias externas al token, con el atributo ValueType como #X509SubjectKeyIdentifier, y su contenido el valor codificado en base64 de la extensión SKI del certificado.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-273">R1202 If a SubjectKeyIdentifier (SKI) extension is present in an X509 certificate, wsse:KeyIdentifier should be used for external references to the token, with the ValueType attribute as #X509SubjectKeyIdentifier and its content the base64-encoded value of certificate's SKI extension.</span></span>  
  
 <span data-ttu-id="2b4e0-274">Las referencias SKI se implementan ampliamente y demuestran ser un tipo de referencia externa muy interoperable.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-274">SKI references are widely implemented and proven to be a highly interoperable external reference type.</span></span>  
  
 <span data-ttu-id="2b4e0-275">R1203 Una referencia externa al token de seguridad X509 NO DEBERÍA utilizar ds:X509IssuerSerial.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-275">R1203 An external Reference to X509 Security Token SHOULD NOT use ds:X509IssuerSerial.</span></span>  
  
 <span data-ttu-id="2b4e0-276">R1204 Si se está utilizando X509TokenProfile1.1, una referencia externa al token de seguridad X509 DEBERÍA utilizar la huella digital introducida por WS-Security 1.1.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-276">R1204 If X509TokenProfile1.1 is in use, an external reference to X509 Security Token SHOULD use the thumbprint introduced by WS-Security 1.1.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="2b4e0-277"> admite X509IssuerSerial.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-277"> supports X509IssuerSerial.</span></span> <span data-ttu-id="2b4e0-278">Sin embargo, hay problemas de interoperabilidad con X509IssuerSerial: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utiliza una cadena para comparar dos valores de X509IssuerSerial.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-278">However There are interoperability issues with X509IssuerSerial: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uses a string to compare two values of X509IssuerSerial.</span></span> <span data-ttu-id="2b4e0-279">Por consiguiente, si uno reordena componentes del Nombre del asunto y envía una referencia a un certificado a un servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], puede que no se encuentre.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-279">Therefore if one reorders components of the Subject Name and sends to an [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service a reference to a certificate, it may not be found.</span></span>  
  
### <a name="13-kerberos-token"></a><span data-ttu-id="2b4e0-280">1.3 Token de Kerberos.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-280">1.3 Kerberos Token</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="2b4e0-281"> admite KerberosTokenProfile1.1 para la autenticación de Windows con las restricciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="2b4e0-281"> supports KerberosTokenProfile1.1 for the purpose of Windows authentication with the following constraints:</span></span>  
  
 <span data-ttu-id="2b4e0-282">R1301 Un Token de Kerberos debe llevar el valor de un AP_REQ de Kerberos v4 ajustado a GSS, tal y como se define en GSS_API y en la especificación de Kerberos, y debe tener el atributo ValueType con el valor #GSS_Kerberosv5_AP_REQ.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-282">R1301 A Kerberos Token must carry the value of a GSS wrapped Kerberos v4 AP_REQ as defined in GSS_API and the Kerberos specification, and must have the ValueType attribute with the value #GSS_Kerberosv5_AP_REQ.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="2b4e0-283"> utiliza AP-REQ de Kerberos ajustado a GSS, no un AP-REQ desnudo.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-283"> uses GSS wrapped Kerberos AP-REQ, not a bare AP-REQ.</span></span> <span data-ttu-id="2b4e0-284">Éste es un procedimiento de seguridad recomendado.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-284">This is a security best practice.</span></span>  
  
### <a name="14-saml-v11-token"></a><span data-ttu-id="2b4e0-285">1.4 Token SAML v1.1</span><span class="sxs-lookup"><span data-stu-id="2b4e0-285">1.4 SAML v1.1 Token</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="2b4e0-286"> admite perfiles de token de WSS SAML 1.0 y 1.1 para tokens SAML v1.1.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-286"> supports WSS SAML Token profiles 1.0 and 1.1 for SAML v1.1 tokens.</span></span> <span data-ttu-id="2b4e0-287">Es posible implementar otras versiones de formatos de token SAML.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-287">It is possible to implement other versions of SAML token formats.</span></span>  
  
### <a name="15-security-context-token"></a><span data-ttu-id="2b4e0-288">1.5 Token de contexto de seguridad</span><span class="sxs-lookup"><span data-stu-id="2b4e0-288">1.5 Security Context Token</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="2b4e0-289"> admite el token de contexto de seguridad (SCT) introducido en WS-SecureCoversation.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-289"> supports the Security Context Token (SCT) introduced in WS-SecureCoversation.</span></span> <span data-ttu-id="2b4e0-290">SCT se utiliza para representar un contexto de seguridad establecido en SecureConversation así como los protocolos de negociación binarios TLS y SSPI, descritos a continuación.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-290">SCT is used to represent a security context established in SecureConversation as well as the binary negotiation protocols TLS and SSPI, described below.</span></span>  
  
## <a name="2-common-message-security-parameters"></a><span data-ttu-id="2b4e0-291">2. Parámetros de seguridad de mensajes comunes</span><span class="sxs-lookup"><span data-stu-id="2b4e0-291">2. Common Message Security Parameters</span></span>  
  
### <a name="21-timestamp"></a><span data-ttu-id="2b4e0-292">2.1 Marca de tiempo</span><span class="sxs-lookup"><span data-stu-id="2b4e0-292">2.1 TimeStamp</span></span>  
 <span data-ttu-id="2b4e0-293">La presencia de la marca de tiempo se controla mediante la propiedad <xref:System.ServiceModel.Channels.SecurityBindingElement.IncludeTimestamp%2A> de la clase <xref:System.ServiceModel.Channels.SecurityBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-293">Timestamp presence is controlled using the <xref:System.ServiceModel.Channels.SecurityBindingElement.IncludeTimestamp%2A> property of the <xref:System.ServiceModel.Channels.SecurityBindingElement> class.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="2b4e0-294"> serializa siempre wsse:TimeStamp con los campos wsse:Created y wsse:Expires.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-294"> always serializes wsse:TimeStamp with wsse:Created and wsse:Expires fields.</span></span> <span data-ttu-id="2b4e0-295">El wsse:TimeStamp siempre se firma cuando se utilizan las firmas.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-295">The wsse:TimeStamp is always signed when signing is used.</span></span>  
  
### <a name="22-protection-order"></a><span data-ttu-id="2b4e0-296">2.2 Orden de protección</span><span class="sxs-lookup"><span data-stu-id="2b4e0-296">2.2 Protection Order</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="2b4e0-297"> admite el orden de protección de mensajes "Sign Before Encrypt" (firmar antes de cifrar) y "Encrypt Before Sign" (cifrar antes de firmar) (Security Policy 1.1).</span><span class="sxs-lookup"><span data-stu-id="2b4e0-297"> supports the message protection order "Sign Before Encrypt" and "Encrypt Before Sign" (Security Policy 1.1).</span></span> <span data-ttu-id="2b4e0-298">"Sign Before Encrypt" se recomienda por diferentes motivos, entre los que se incluyen los siguientes: los mensajes protegidos mediante Encrypt Before Sign están expuestos a ataques de sustitución de firmas a menos que se use el mecanismo SignatureConfirmation de WS-Security 1.1, y una firma sobre el contenido cifrado dificulta la auditoría.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-298">"Sign Before Encrypt" is recommended for reasons including: messages protected with Encrypt Before Sign are open to signature substitution attacks unless the WS-Security 1.1 SignatureConfirmation mechanism is used, and a signature over encrypted content makes auditing harder.</span></span>  
  
### <a name="23-signature-protection"></a><span data-ttu-id="2b4e0-299">2.3 Protección de firmas</span><span class="sxs-lookup"><span data-stu-id="2b4e0-299">2.3 Signature Protection</span></span>  
 <span data-ttu-id="2b4e0-300">Cuando se usa Cifrar antes de firmar, se recomienda proteger la firma para evitar los ataques por fuerza bruta para adivinar el contenido cifrado o la clave de la firma (sobre todo cuando un token personalizado se utiliza con material de clave débil).</span><span class="sxs-lookup"><span data-stu-id="2b4e0-300">When Encrypt Before Sign is used, it is recommended to protect the signature to prevent brute force attacks for guessing the encrypted content or the signing key (especially when a custom token is used with weak key material).</span></span>  
  
### <a name="24-algorithm-suite"></a><span data-ttu-id="2b4e0-301">2.4 Conjunto de algoritmos</span><span class="sxs-lookup"><span data-stu-id="2b4e0-301">2.4 Algorithm Suite</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="2b4e0-302"> admite todos los conjuntos de algoritmos enumerados en la Directiva de seguridad 1.1.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-302"> supports all algorithm suites listed in Security Policy 1.1.</span></span>  
  
### <a name="25-key-derivation"></a><span data-ttu-id="2b4e0-303">2.5 Derivación de clave</span><span class="sxs-lookup"><span data-stu-id="2b4e0-303">2.5 Key Derivation</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="2b4e0-304"> utiliza la "Derivación de clave para claves simétricas" tal y como se describe en WS-SecureConversation.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-304"> uses "Key Derivation for symmetric keys" as described in WS-SecureConversation.</span></span>  
  
### <a name="26-signature-confirmation"></a><span data-ttu-id="2b4e0-305">2.6 Confirmación de firma</span><span class="sxs-lookup"><span data-stu-id="2b4e0-305">2.6 Signature Confirmation</span></span>  
 <span data-ttu-id="2b4e0-306">La confirmación de firma puede ser como protección frente a ataques de intermediarios para proteger el conjunto de firmas.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-306">Signature confirmation can be as protection from middle man attacks to protect the set of signatures.</span></span>  
  
### <a name="27-security-header-layout"></a><span data-ttu-id="2b4e0-307">2.7 Diseño del encabezado de seguridad</span><span class="sxs-lookup"><span data-stu-id="2b4e0-307">2.7 Security Header Layout</span></span>  
 <span data-ttu-id="2b4e0-308">Cada modo de autenticación describe un cierto diseño para el encabezado de seguridad.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-308">Each authentication mode describes a certain layout for the security header.</span></span> <span data-ttu-id="2b4e0-309">Los elementos dentro del encabezado de seguridad se semiordenan.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-309">Elements within the security header are semi-ordered.</span></span> <span data-ttu-id="2b4e0-310">Para definir el orden de elementos secundarios del encabezado de seguridad, la directiva WS-Security define los siguientes modos de diseño del encabezado de seguridad:</span><span class="sxs-lookup"><span data-stu-id="2b4e0-310">To define the order of security header child elements, WS-Security Policy defines the following security header layout modes:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2b4e0-311">Strict</span><span class="sxs-lookup"><span data-stu-id="2b4e0-311">Strict</span></span>|<span data-ttu-id="2b4e0-312">Los elementos se agregan al encabezado de seguridad siguiendo las reglas de diseño descritas en la sección 7.7.1 de la Directiva de seguridad, según un principio general de "declarar antes de usar".</span><span class="sxs-lookup"><span data-stu-id="2b4e0-312">Items are added to the security header following the numbered layout rules described in Security Policy section 7.7.1 according to a general principle of "declare before use".</span></span>|  
|<span data-ttu-id="2b4e0-313">Lax</span><span class="sxs-lookup"><span data-stu-id="2b4e0-313">Lax</span></span>|<span data-ttu-id="2b4e0-314">Los elementos se agregan al encabezado de seguridad en cualquier orden que cumpla con la seguridad de mensajes WSS: SOAP.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-314">Items are added to the security header in any order that conforms to WSS: SOAP Message Security.</span></span>|  
|<span data-ttu-id="2b4e0-315">LaxTimestampFirst</span><span class="sxs-lookup"><span data-stu-id="2b4e0-315">LaxTimestampFirst</span></span>|<span data-ttu-id="2b4e0-316">Igual que Lax, solo que el primer elemento en el encabezado de seguridad debe ser wsse:Timestamp</span><span class="sxs-lookup"><span data-stu-id="2b4e0-316">Same as Lax except that the first item in the security header must be a wsse:Timestamp</span></span>|  
|<span data-ttu-id="2b4e0-317">LaxTimestampLast</span><span class="sxs-lookup"><span data-stu-id="2b4e0-317">LaxTimestampLast</span></span>|<span data-ttu-id="2b4e0-318">Igual que lax, solo que el último elemento en el encabezado de seguridad debe ser wsse:Timestamp</span><span class="sxs-lookup"><span data-stu-id="2b4e0-318">Same as lax except that the last item in the security header must be a wsse:Timestamp</span></span>|  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="2b4e0-319"> admite los cuatro modos de diseño del encabezado de seguridad.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-319"> supports all four modes for security header layout.</span></span> <span data-ttu-id="2b4e0-320">La estructura de encabezado de Seguridad y los ejemplos de mensajes para los modos de autenticación siguen el modo "Strict" (estricto).</span><span class="sxs-lookup"><span data-stu-id="2b4e0-320">Security header structure and message examples for authentication modes below follow the "Strict" mode.</span></span>  
  
## <a name="2-common-message-security-parameters"></a><span data-ttu-id="2b4e0-321">2. Parámetros de seguridad de mensajes comunes</span><span class="sxs-lookup"><span data-stu-id="2b4e0-321">2. Common Message Security Parameters</span></span>  
 <span data-ttu-id="2b4e0-322">En esta sección se proporcionan ejemplos de directivas para cada modo de autenticación junto con ejemplos que muestran la estructura de encabezado de seguridad en mensajes intercambiados por cliente y servicio.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-322">This section provides example policies for each authentication mode along with examples showing security header structure in messages exchanged by client and service.</span></span>  
  
### <a name="61-transport-protection"></a><span data-ttu-id="2b4e0-323">6.1 Protección de transporte</span><span class="sxs-lookup"><span data-stu-id="2b4e0-323">6.1 Transport Protection</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="2b4e0-324"> proporciona cinco modos de autenticación que utilizan el transporte seguro para proteger los mensajes; UserNameOverTransport, CertificateOverTransport, KerberosOverTransport, IssuedTokenOverTransport y SspiNegotiatedOverTransport.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-324"> provides five authentication modes that use secure transport to protect messages; UserNameOverTransport, CertificateOverTransport, KerberosOverTransport, IssuedTokenOverTransport and SspiNegotiatedOverTransport.</span></span>  
  
 <span data-ttu-id="2b4e0-325">Estos modos de autenticación se construyen utilizando el enlace de transportes descrito en SecurityPolicy.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-325">These authentication modes are constructed using the transport binding described in SecurityPolicy.</span></span> <span data-ttu-id="2b4e0-326">Para el modo de autenticación de UserNameOverTransport, UsernameToken es un token auxiliar firmado.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-326">For the UserNameOverTransport authentication mode the UsernameToken is a signed supporting token.</span></span> <span data-ttu-id="2b4e0-327">Para los otros modos de autenticación el token aparece como un token de endoso firmado.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-327">For the other authentication modes the token appears as a signed endorsing token.</span></span> <span data-ttu-id="2b4e0-328">Los apéndices C.1.2 y C.1.3 de SecurityPolicy describen en detalle el diseño del encabezado de seguridad.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-328">Appendix C.1.2 and C.1.3 of SecurityPolicy describe the security header layout in detail.</span></span> <span data-ttu-id="2b4e0-329">Los siguientes encabezados de seguridad del ejemplo muestran el diseño estricto para un modo de autenticación determinado.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-329">The following example security headers show the Strict layout for a given authentication mode.</span></span>  
  
 <span data-ttu-id="2b4e0-330">El valor de propiedad “Derived Keys” para los tokens en todos los casos es "falsa."</span><span class="sxs-lookup"><span data-stu-id="2b4e0-330">The value of the "Derived Keys" property for the tokens in all cases is "false".</span></span>  
  
 <span data-ttu-id="2b4e0-331">Los valores de las diversas propiedades del enlace de transporte son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="2b4e0-331">The values of the various properties of the transport binding are as follows:</span></span>  
  
 <span data-ttu-id="2b4e0-332">Marca de tiempo: true</span><span class="sxs-lookup"><span data-stu-id="2b4e0-332">Timestamp: true</span></span>  
  
 <span data-ttu-id="2b4e0-333">Diseño de encabezado de seguridad: Strict</span><span class="sxs-lookup"><span data-stu-id="2b4e0-333">Security Header Layout: Strict</span></span>  
  
 <span data-ttu-id="2b4e0-334">Conjunto de algoritmos: Basic256</span><span class="sxs-lookup"><span data-stu-id="2b4e0-334">Algorithm Suite: Basic256</span></span>  
  
#### <a name="611-usernameovertransport"></a><span data-ttu-id="2b4e0-335">6.1.1 UsernameOverTransport</span><span class="sxs-lookup"><span data-stu-id="2b4e0-335">6.1.1 UsernameOverTransport</span></span>  
 <span data-ttu-id="2b4e0-336">Con este modo de autenticación, el cliente se autentica con un token de nombre de usuario que aparece en la capa de SOAP como un token auxiliar firmado que siempre se envía desde el iniciador al destinatario.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-336">With this authentication mode, the client authenticates with a Username Token which appears at the SOAP layer as a signed supporting token that is always sent from the initiator to the recipient.</span></span> <span data-ttu-id="2b4e0-337">La autenticación del servicio se realiza mediante un certificado X.509 en el nivel de transporte.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-337">The service is authenticated using an X.509 certificate at the transport layer.</span></span> <span data-ttu-id="2b4e0-338">El enlace utilizado es un enlace de transporte.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-338">The binding used is a transport binding.</span></span>  
  
 <span data-ttu-id="2b4e0-339">Directiva</span><span class="sxs-lookup"><span data-stu-id="2b4e0-339">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='UsernameOverTransport_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:TransportBinding >  
        <wsp:Policy>  
          <sp:TransportToken>  
            <wsp:Policy>  
              <sp:HttpsToken RequireClientCertificate='false' />   
            </wsp:Policy>  
          </sp:TransportToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />   
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />   
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />   
        </wsp:Policy>  
      </sp:TransportBinding>  
      <sp:SignedSupportingTokens >  
        <wsp:Policy>  
          <sp:UsernameToken   
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
            <wsp:Policy>  
              <sp:WssUsernameToken10 />   
            </wsp:Policy>  
          </sp:UsernameToken>  
        </wsp:Policy>  
      </sp:SignedSupportingTokens>  
      <sp:Wss11 >  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />   
          <sp:MustSupportRefIssuerSerial />   
          <sp:MustSupportRefThumbprint />   
          <sp:MustSupportRefEncryptedKey />   
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10 >  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />   
          <sp:RequireClientEntropy />   
          <sp:RequireServerEntropy />   
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />   
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
 <span data-ttu-id="2b4e0-340">Diseño del encabezado de seguridad</span><span class="sxs-lookup"><span data-stu-id="2b4e0-340">Security Header Layout</span></span>  
  
 <span data-ttu-id="2b4e0-341">Request</span><span class="sxs-lookup"><span data-stu-id="2b4e0-341">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wsse:UsernameToken ... >  
  ...  
  </wsse:UsernameToken>  
</wsse:Security>  
```  
  
 <span data-ttu-id="2b4e0-342">Respuesta</span><span class="sxs-lookup"><span data-stu-id="2b4e0-342">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
</wsse:Security>  
```  
  
#### <a name="612-certificateovertransport"></a><span data-ttu-id="2b4e0-343">6.1.2 CertificateOverTransport</span><span class="sxs-lookup"><span data-stu-id="2b4e0-343">6.1.2 CertificateOverTransport</span></span>  
 <span data-ttu-id="2b4e0-344">Con este modo de autenticación el cliente se autentica utilizando un certificado X.509 que aparece en la capa de SOAP como un token auxiliar de aprobación que siempre se envía desde el iniciador al destinatario.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-344">With this authentication mode the client authenticates using an X.509 certificate which appears at the SOAP layer as an endorsing supporting token that is always sent from the initiator to the recipient.</span></span> <span data-ttu-id="2b4e0-345">La autenticación del servicio se realiza mediante un certificado X.509 en el nivel de transporte.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-345">The service is authenticated using an X.509 certificate at the transport layer.</span></span> <span data-ttu-id="2b4e0-346">El enlace utilizado es un enlace de transporte.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-346">The binding used is a transport binding.</span></span>  
  
 <span data-ttu-id="2b4e0-347">Directiva</span><span class="sxs-lookup"><span data-stu-id="2b4e0-347">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='CertificateOverTransport_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:TransportBinding xmlns:sp='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy' >  
        <wsp:Policy>  
          <sp:TransportToken>  
            <wsp:Policy>  
             <sp:HttpsToken RequireClientCertificate='false' />   
            </wsp:Policy>  
          </sp:TransportToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />   
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />   
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />   
        </wsp:Policy>  
      </sp:TransportBinding>  
      <sp:EndorsingSupportingTokens>  
        <wsp:Policy>  
          <sp:X509Token   
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
            <wsp:Policy>  
              <sp:RequireThumbprintReference />   
              <sp:WssX509V3Token10 />   
            </wsp:Policy>  
          </sp:X509Token>  
          <sp:SignedParts>  
            <sp:Header Name='To'   
Namespace='http://www.w3.org/2005/08/addressing' />   
          </sp:SignedParts>  
        </wsp:Policy>  
      </sp:EndorsingSupportingTokens>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />   
          <sp:MustSupportRefIssuerSerial />   
          <sp:MustSupportRefThumbprint />   
          <sp:MustSupportRefEncryptedKey />   
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />   
          <sp:RequireClientEntropy />   
          <sp:RequireServerEntropy />   
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />   
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
 <span data-ttu-id="2b4e0-348">Diseño del encabezado de seguridad</span><span class="sxs-lookup"><span data-stu-id="2b4e0-348">Security Header Layout</span></span>  
  
 <span data-ttu-id="2b4e0-349">Request</span><span class="sxs-lookup"><span data-stu-id="2b4e0-349">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wse:Timestamp u:Id="_0">  
  ...  
  </wse:Timestamp>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
</wsse:Security>  
```  
  
 <span data-ttu-id="2b4e0-350">Respuesta</span><span class="sxs-lookup"><span data-stu-id="2b4e0-350">Response</span></span>  
  
```xml  
<o:Security>  
  <u:Timestamp u:Id="_0">  
  ...  
  </u:Timestamp>  
</o:Security>  
```  
  
#### <a name="613-issuedtokenovertransport"></a><span data-ttu-id="2b4e0-351">6.1.3 IssuedTokenOverTransport</span><span class="sxs-lookup"><span data-stu-id="2b4e0-351">6.1.3 IssuedTokenOverTransport</span></span>  
 <span data-ttu-id="2b4e0-352">Con este modo de autenticación, el cliente no se autentica al servicio como tal; sino que, en su lugar, presenta un token emitido por un servicio de token de seguridad (STS) y demuestra que conoce una clave compartida.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-352">With this authentication mode the client does not authenticate to the service, as such, but rather presents a token issued by a Security Token Service (STS) and proves knowledge of a shared key.</span></span> <span data-ttu-id="2b4e0-353">El token emitido aparece en la capa de SOAP como un token auxiliar de aprobación que siempre se envía desde el iniciador al destinatario.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-353">The issued token appears at the SOAP layer as an endorsing supporting token that is always sent from the initiator to the recipient.</span></span> <span data-ttu-id="2b4e0-354">La autenticación del servicio se realiza mediante un certificado X.509 en el nivel de transporte.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-354">The service is authenticated using an X.509 certificate at the transport layer.</span></span> <span data-ttu-id="2b4e0-355">El enlace es un enlace de transporte.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-355">The binding is a transport binding.</span></span>  
  
 <span data-ttu-id="2b4e0-356">Directiva</span><span class="sxs-lookup"><span data-stu-id="2b4e0-356">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='IssuedTokenOverTransport_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:TransportBinding >  
        <wsp:Policy>  
          <sp:TransportToken>  
            <wsp:Policy>  
              <sp:HttpsToken RequireClientCertificate='false' />   
            </wsp:Policy>  
          </sp:TransportToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />   
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />   
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />   
        </wsp:Policy>  
      </sp:TransportBinding>  
      <sp:EndorsingSupportingTokens>  
        <wsp:Policy>  
          <sp:IssuedToken   
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
            <sp:RequestSecurityTokenTemplate>  
              <wst:KeyType>  
              http://schemas.xmlsoap.org/ws/2005/02/trust/SymmetricKey  
              </wst:KeyType>   
            </sp:RequestSecurityTokenTemplate>  
            <wsp:Policy>  
              <sp:RequireInternalReference />   
            </wsp:Policy>  
          </sp:IssuedToken>  
          <sp:SignedParts>  
            <sp:Header Name='To'   
Namespace='http://www.w3.org/2005/08/addressing' />   
          </sp:SignedParts>  
        </wsp:Policy>  
      </sp:EndorsingSupportingTokens>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />   
          <sp:MustSupportRefIssuerSerial />   
          <sp:MustSupportRefThumbprint />   
          <sp:MustSupportRefEncryptedKey />   
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />   
          <sp:RequireClientEntropy />   
          <sp:RequireServerEntropy />   
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />   
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
 <span data-ttu-id="2b4e0-357">Diseño del encabezado de seguridad</span><span class="sxs-lookup"><span data-stu-id="2b4e0-357">Security Header Layout</span></span>  
  
 <span data-ttu-id="2b4e0-358">Request</span><span class="sxs-lookup"><span data-stu-id="2b4e0-358">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1" >  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <saml:Assertion ...>  
  ...  
  </saml:Assertion>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
</wsse:Security>  
```  
  
 <span data-ttu-id="2b4e0-359">Respuesta</span><span class="sxs-lookup"><span data-stu-id="2b4e0-359">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
</wsse:Security>  
```  
  
#### <a name="614-kerberosovertransport"></a><span data-ttu-id="2b4e0-360">6.1.4 KerberosOverTransport</span><span class="sxs-lookup"><span data-stu-id="2b4e0-360">6.1.4 KerberosOverTransport</span></span>  
 <span data-ttu-id="2b4e0-361">Con este modo de autenticación, el cliente se autentica en el servicio utilizando un tique de Kerberos.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-361">With this authentication mode the client authenticates to the service using a Kerberos ticket.</span></span> <span data-ttu-id="2b4e0-362">El token de Kerberos aparece en la capa de SOAP como un token auxiliar de aprobación.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-362">The Kerberos token appears at the SOAP layer as an endorsing supporting token.</span></span> <span data-ttu-id="2b4e0-363">La autenticación del servicio se realiza mediante un certificado X.509 en el nivel de transporte.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-363">The service is authenticated using an X.509 certificate at the transport layer.</span></span> <span data-ttu-id="2b4e0-364">El enlace es un enlace de transporte.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-364">The binding is a transport binding.</span></span>  
  
 <span data-ttu-id="2b4e0-365">Directiva</span><span class="sxs-lookup"><span data-stu-id="2b4e0-365">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='KerberosOverTransport_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:TransportBinding>  
        <wsp:Policy>  
          <sp:TransportToken>  
            <wsp:Policy>  
              <sp:HttpsToken RequireClientCertificate='false' />   
            </wsp:Policy>  
          </sp:TransportToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic128 />   
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />   
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />   
        </wsp:Policy>  
      </sp:TransportBinding>  
      <sp:EndorsingSupportingTokens>  
        <wsp:Policy>  
          <sp:KerberosToken  
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/Once' >  
            <wsp:Policy>  
              <sp:WssGssKerberosV5ApReqToken11 />   
            </wsp:Policy>  
          </sp:KerberosToken>  
          <sp:SignedParts>  
            <sp:Header Name='To'   
Namespace='http://www.w3.org/2005/08/addressing' />   
          </sp:SignedParts>  
        </wsp:Policy>  
      </sp:EndorsingSupportingTokens>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />   
          <sp:MustSupportRefIssuerSerial />   
          <sp:MustSupportRefThumbprint />   
          <sp:MustSupportRefEncryptedKey />   
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />   
          <sp:RequireClientEntropy />   
          <sp:RequireServerEntropy />   
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />   
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
 <span data-ttu-id="2b4e0-366">Diseño del encabezado de seguridad</span><span class="sxs-lookup"><span data-stu-id="2b4e0-366">Security Header Layout</span></span>  
  
 <span data-ttu-id="2b4e0-367">Request</span><span class="sxs-lookup"><span data-stu-id="2b4e0-367">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1" >  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wsse:BinarySecurityToken ValueType="...#GSS_Kerberosv5_AP_REQ">  
  ...  
  </wsse:BinarySecurityToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
</wsse:Security>  
```  
  
 <span data-ttu-id="2b4e0-368">Respuesta</span><span class="sxs-lookup"><span data-stu-id="2b4e0-368">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
</wsse:Security>  
```  
  
#### <a name="615-sspinegotiatedovertransport"></a><span data-ttu-id="2b4e0-369">6.1.5 SspiNegotiatedOverTransport</span><span class="sxs-lookup"><span data-stu-id="2b4e0-369">6.1.5 SspiNegotiatedOverTransport</span></span>  
 <span data-ttu-id="2b4e0-370">Con este modo de negociación, se usa un protocolo de negociación para realizar la autenticación del cliente y del servidor.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-370">With this mode a negotiation protocol is used to perform client and server authentication.</span></span> <span data-ttu-id="2b4e0-371">Se utiliza Kerberos si es posible; de lo contrario, se utiliza NTLM.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-371">Kerberos is used if possible, otherwise NTLM.</span></span> <span data-ttu-id="2b4e0-372">El SCT resultante aparece en la capa de SOAP como un token auxiliar de aprobación que siempre se envía desde el iniciador al destinatario.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-372">The resulting SCT appears at the SOAP layer as an endorsing supporting token that is always sent from initiator to recipient.</span></span> <span data-ttu-id="2b4e0-373">El servicio se autentica además en el nivel de transporte por un certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-373">The service is additionally authenticated at the transport layer by an X.509 certificate.</span></span> <span data-ttu-id="2b4e0-374">El enlace utilizado es un enlace de transporte.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-374">The binding used is a transport binding.</span></span> <span data-ttu-id="2b4e0-375">"SPNEGO" (negociación) describe cómo [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utiliza el protocolo de negociación binario SSPI con WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-375">"SPNEGO" (negotiation) describes how [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uses SSPI binary negotiation protocol with WS-Trust.</span></span> <span data-ttu-id="2b4e0-376">Los ejemplos de encabezados de seguridad de esta sección tienen lugar una vez se ha establecido SCT mediante el protocolo de enlace SPNEGO.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-376">Security header examples in this section are after the SCT has been established through the SPNEGO handshake.</span></span>  
  
 <span data-ttu-id="2b4e0-377">Directiva</span><span class="sxs-lookup"><span data-stu-id="2b4e0-377">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='SspiNegotiatedOverTransport_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:TransportBinding>  
        <wsp:Policy>  
          <sp:TransportToken>  
            <wsp:Policy>  
              <sp:HttpsToken RequireClientCertificate='false' />   
            </wsp:Policy>  
          </sp:TransportToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />   
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />   
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />   
        </wsp:Policy>  
      </sp:TransportBinding>  
      <sp:EndorsingSupportingTokens>  
        <wsp:Policy>  
          <sp:SpnegoContextToken   
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
            <wsp:Policy />   
          </sp:SpnegoContextToken>  
          <sp:SignedParts>  
            <sp:Header Name='To'   
Namespace='http://www.w3.org/2005/08/addressing' />   
          </sp:SignedParts>  
        </wsp:Policy>  
      </sp:EndorsingSupportingTokens>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />   
          <sp:MustSupportRefIssuerSerial />   
          <sp:MustSupportRefThumbprint />   
          <sp:MustSupportRefEncryptedKey />   
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />   
          <sp:RequireClientEntropy />   
          <sp:RequireServerEntropy />   
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />   
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### <a name="security-header-examples"></a><span data-ttu-id="2b4e0-378">Ejemplos de encabezados de seguridad</span><span class="sxs-lookup"><span data-stu-id="2b4e0-378">Security Header Examples</span></span>  
 <span data-ttu-id="2b4e0-379">Una vez se establece el token de contexto de seguridad (SCT) a través del protocolo de enlace de SPNEGO mediante negociación binaria WS-Trust, los mensajes de aplicación tienen encabezados de seguridad con la estructura siguiente.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-379">Once the Security Context Token is established through SPNEGO handshake using WS-Trust Binary Negotiation, the application messages have security headers with the following structure.</span></span>  
  
 <span data-ttu-id="2b4e0-380">Request</span><span class="sxs-lookup"><span data-stu-id="2b4e0-380">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:SecurityContextToken u:Id="uuid-2202746a-7725-453d-8747-809cb718dab0-29" >  
  ...  
  </wssc:SecurityContextToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
</wsse:Security>  
```  
  
 <span data-ttu-id="2b4e0-381">Respuesta</span><span class="sxs-lookup"><span data-stu-id="2b4e0-381">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
</wsse:Security>  
```  
  
### <a name="62-using-x509-certificates-for-service-authentication"></a><span data-ttu-id="2b4e0-382">6.2 Uso de certificados X.509 para la autenticación de servicios</span><span class="sxs-lookup"><span data-stu-id="2b4e0-382">6.2 Using X.509 Certificates for Service Authentication</span></span>  
 <span data-ttu-id="2b4e0-383">En esta sección se describen los modos de autenticación siguientes: MutualCertificate WSS1.0, Mutual CertificateDuplex, MutualCertificate WSS1.1, AnonymousForCertificate, UserNameForCertificate y IssuedTokenForCertificate.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-383">This section describes the following authentication modes: MutualCertificate WSS1.0, Mutual CertificateDuplex, MutualCertificate WSS1.1, AnonymousForCertificate, UserNameForCertificate and IssuedTokenForCertificate.</span></span>  
  
#### <a name="621-mutualcertificate-wss10"></a><span data-ttu-id="2b4e0-384">6.2.1 MutualCertificate WSS1.0</span><span class="sxs-lookup"><span data-stu-id="2b4e0-384">6.2.1 MutualCertificate WSS1.0</span></span>  
 <span data-ttu-id="2b4e0-385">Con este modo de autenticación el cliente autentica mediante un certificado X.509 que aparece en la capa de SOAP como el token del iniciador.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-385">With this authentication mode the client authenticates using an X.509 certificate which appears at the SOAP layer as the initiator token.</span></span> <span data-ttu-id="2b4e0-386">La autenticación del servicio también se realiza mediante un certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-386">The service is also authenticated using an X.509 certificate.</span></span>  
  
 <span data-ttu-id="2b4e0-387">El enlace usado es un enlace asimétrico con los valores de propiedad siguientes:</span><span class="sxs-lookup"><span data-stu-id="2b4e0-387">The binding used is an asymmetric binding with the following property values:</span></span>  
  
 <span data-ttu-id="2b4e0-388">Token del iniciador: el certificado X.509 del cliente, con modo de inclusión establecido en …/IncludeToken/AlwaysToRecipient</span><span class="sxs-lookup"><span data-stu-id="2b4e0-388">Initiator Token: the client’s X.509 certificate, with inclusion mode set to …/IncludeToken/AlwaysToRecipient</span></span>  
  
 <span data-ttu-id="2b4e0-389">Token del destinatario: el certificado X.509 del servidor, con modo de inclusión establecido en …/IncludeToken/Never</span><span class="sxs-lookup"><span data-stu-id="2b4e0-389">Recipient Token: Server’s X.509 Certificate, with inclusion mode is set …/IncludeToken/Never</span></span>  
  
 <span data-ttu-id="2b4e0-390">Protección de tokens: False</span><span class="sxs-lookup"><span data-stu-id="2b4e0-390">Token Protection: False</span></span>  
  
 <span data-ttu-id="2b4e0-391">Encabezado completo y firmas de cuerpo: True</span><span class="sxs-lookup"><span data-stu-id="2b4e0-391">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="2b4e0-392">Orden de protección: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="2b4e0-392">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="2b4e0-393">Cifrar firma: True</span><span class="sxs-lookup"><span data-stu-id="2b4e0-393">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="2b4e0-394">Directiva</span><span class="sxs-lookup"><span data-stu-id="2b4e0-394">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='MutualCertificate_WSS10_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:AsymmetricBinding>  
        <wsp:Policy>  
          <sp:InitiatorToken>  
            <wsp:Policy>  
              <sp:X509Token   
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
                <wsp:Policy>  
                  <sp:WssX509V3Token10 />   
                </wsp:Policy>  
              </sp:X509Token>  
            </wsp:Policy>  
          </sp:InitiatorToken>  
          <sp:RecipientToken>  
            <wsp:Policy>  
              <sp:X509Token   
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/Never' >  
                <wsp:Policy>  
                  <sp:WssX509V3Token10 />   
                </wsp:Policy>  
              </sp:X509Token>  
            </wsp:Policy>  
          </sp:RecipientToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />   
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />   
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />   
          <sp:EncryptSignature />   
          <sp:OnlySignEntireHeadersAndBody />   
        </wsp:Policy>  
      </sp:AsymmetricBinding>  
      <sp:Wss10>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />   
          <sp:MustSupportRefIssuerSerial />   
        </wsp:Policy>  
      </sp:Wss10>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />   
          <sp:RequireClientEntropy />   
          <sp:RequireServerEntropy />   
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />   
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="2b4e0-395">Ejemplos de encabezado de seguridad: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="2b4e0-395">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="2b4e0-396">Request</span><span class="sxs-lookup"><span data-stu-id="2b4e0-396">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <xenc:EncryptedKey>  
  ...  
    <xenc:ReferenceList>  
    ...  
    </xenc:ReferenceList>  
  </xenc:EncryptedKey>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="2b4e0-397">Respuesta</span><span class="sxs-lookup"><span data-stu-id="2b4e0-397">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
    <xenc:ReferenceList>  
    ...  
    </xenc:ReferenceList>  
  </xenc:EncryptedKey>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="2b4e0-398">Ejemplos de encabezado de seguridad: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="2b4e0-398">Security Header Examples: EncryptBeforeSign</span></span>  
  
 <span data-ttu-id="2b4e0-399">Request</span><span class="sxs-lookup"><span data-stu-id="2b4e0-399">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="2b4e0-400">Respuesta</span><span class="sxs-lookup"><span data-stu-id="2b4e0-400">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="622-mutualcertificateduplex"></a><span data-ttu-id="2b4e0-401">6.2.2 MutualCertificateDuplex</span><span class="sxs-lookup"><span data-stu-id="2b4e0-401">6.2.2 MutualCertificateDuplex</span></span>  
 <span data-ttu-id="2b4e0-402">Con este modo de autenticación el cliente autentica mediante un certificado X.509 que aparece en la capa de SOAP como el token del iniciador.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-402">With this authentication mode the client authenticates using an X.509 certificate which appears at the SOAP layer as the initiator token.</span></span> <span data-ttu-id="2b4e0-403">La autenticación del servicio también se realiza mediante un certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-403">The service is also authenticated using an X.509 certificate.</span></span>  
  
 <span data-ttu-id="2b4e0-404">El enlace usado es un enlace asimétrico con los valores de propiedad siguientes:</span><span class="sxs-lookup"><span data-stu-id="2b4e0-404">The binding used is an asymmetric binding with the following property values:</span></span>  
  
 <span data-ttu-id="2b4e0-405">Token del iniciador: certificado X509 de cliente, modo de inclusión establecido en …/IncludeToken/AlwaysToRecipient</span><span class="sxs-lookup"><span data-stu-id="2b4e0-405">Initiator Token: Client’s X509 Certificate, inclusion mode is set to …/IncludeToken/AlwaysToRecipient</span></span>  
  
 <span data-ttu-id="2b4e0-406">Token del destinatario: certificado X509 del servidor, modo de inclusión establecido en …/IncludeToken/AlwaysToInitiator</span><span class="sxs-lookup"><span data-stu-id="2b4e0-406">Recipient Token: Server’s X509 Certificate, inclusion mode is set to …/IncludeToken/AlwaysToInitiator</span></span>  
  
 <span data-ttu-id="2b4e0-407">Protección de tokens: False</span><span class="sxs-lookup"><span data-stu-id="2b4e0-407">Token Protection: False</span></span>  
  
 <span data-ttu-id="2b4e0-408">Encabezado completo y firmas de cuerpo: True</span><span class="sxs-lookup"><span data-stu-id="2b4e0-408">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="2b4e0-409">Orden de protección: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="2b4e0-409">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="2b4e0-410">Cifrar firma: True</span><span class="sxs-lookup"><span data-stu-id="2b4e0-410">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="2b4e0-411">Directiva</span><span class="sxs-lookup"><span data-stu-id="2b4e0-411">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='MutualCertificateDuplex_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:AsymmetricBinding>  
        <wsp:Policy>  
          <sp:InitiatorToken>  
            <wsp:Policy>  
              <sp:X509Token   
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
                <wsp:Policy>  
                  <sp:WssX509V3Token10 />   
                </wsp:Policy>  
              </sp:X509Token>  
            </wsp:Policy>  
          </sp:InitiatorToken>  
          <sp:RecipientToken>  
            <wsp:Policy>  
              <sp:X509Token   
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToInitiator' >  
                <wsp:Policy>  
                  <sp:WssX509V3Token10 />   
                </wsp:Policy>  
              </sp:X509Token>  
            </wsp:Policy>  
          </sp:RecipientToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />   
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />   
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />   
          <sp:EncryptSignature />   
          <sp:OnlySignEntireHeadersAndBody />   
        </wsp:Policy>  
      </sp:AsymmetricBinding>  
      <sp:Wss10>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />   
          <sp:MustSupportRefIssuerSerial />   
        </wsp:Policy>  
      </sp:Wss10>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />   
          <sp:RequireClientEntropy />   
          <sp:RequireServerEntropy />   
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />   
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="2b4e0-412">Ejemplos de encabezado de seguridad: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="2b4e0-412">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="2b4e0-413">Solicitud y respuesta</span><span class="sxs-lookup"><span data-stu-id="2b4e0-413">Request and Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <xenc:EncryptedKey>  
  ...  
    <xenc:ReferenceList>  
    ...  
    </xenc:ReferenceList>  
  </xenc:EncryptedKey>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="2b4e0-414">Ejemplos de encabezado de seguridad: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="2b4e0-414">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="2b4e0-415">Solicitud y respuesta</span><span class="sxs-lookup"><span data-stu-id="2b4e0-415">Request and Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="623-using-symmetricbinding-with-x509-service-authentication"></a><span data-ttu-id="2b4e0-416">6.2.3 Uso de SymmetricBinding con autenticación de servicio X.509</span><span class="sxs-lookup"><span data-stu-id="2b4e0-416">6.2.3 Using SymmetricBinding with X.509 Service Authentication</span></span>  
 <span data-ttu-id="2b4e0-417">"WSS10" proporcionó compatibilidad limitada para escenarios con tokens de X509.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-417">"WSS10" provided limited support for scenarios with X509 tokens.</span></span> <span data-ttu-id="2b4e0-418">Por ejemplo, no hubo manera de proporcionar protección de cifrado y firma para los mensajes que solo usan tokens de X509 de servicio.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-418">For example, there was no way to provide signature and encryption protection for messages using only service X509 token.</span></span> <span data-ttu-id="2b4e0-419">"WSS11" introdujo el uso de EncryptedKey como un token simétrico.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-419">"WSS11" introduced the usage of EncryptedKey as a symmetric token.</span></span> <span data-ttu-id="2b4e0-420">Ahora una clave temporal cifrada para el certificado X.509 de servicio se podría utilizar para la protección de mensajes de solicitud y respuesta.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-420">Now a temporary key encrypted for the service's X.509 certificate could be used for both request and response messages protection.</span></span> <span data-ttu-id="2b4e0-421">Los modos de autenticación descritos en la sección 6.4 que se encuentra abajo usan este patrón.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-421">The authentication modes described in the section 6.4 below use this pattern.</span></span>  
  
 <span data-ttu-id="2b4e0-422">WS-SecurityPolicy describe este patrón utilizando SymmetricBinding con token X509 de servicio como el token de protección.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-422">WS-SecurityPolicy describes this pattern using SymmetricBinding with Service X509 token as the protection token.</span></span>  
  
 <span data-ttu-id="2b4e0-423">Los modos de autenticación AnonymousForCertificate, UsernameForCertificate, MutualCertificate WSS11 e IssuedTokenForCertificate usan una instancia similar de sp:SymmetricBinding con los siguientes valores de propiedad:</span><span class="sxs-lookup"><span data-stu-id="2b4e0-423">Authentication modes AnonymousForCertificate, UsernameForCertificate, MutualCertificate WSS11 and IssuedTokenForCertificate all use a similar instance of sp:SymmetricBinding with the following property values:</span></span>  
  
 <span data-ttu-id="2b4e0-424">Token de protección: certificado X.509 de servidor, modo de inclusión establecido en .../IncludeToken/Never</span><span class="sxs-lookup"><span data-stu-id="2b4e0-424">Protection Token: Server’s X509 Certificate, inclusion mode is set to .../IncludeToken/Never</span></span>  
<span data-ttu-id="2b4e0-425">Protección de tokens: False</span><span class="sxs-lookup"><span data-stu-id="2b4e0-425">Token Protection: False</span></span>  
  
 <span data-ttu-id="2b4e0-426">Encabezado completo y firmas de cuerpo: True</span><span class="sxs-lookup"><span data-stu-id="2b4e0-426">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="2b4e0-427">Orden de protección: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="2b4e0-427">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="2b4e0-428">Cifrar firma: True</span><span class="sxs-lookup"><span data-stu-id="2b4e0-428">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="2b4e0-429">Los modos de autenticación anteriores solo difieren en los tokens auxiliares que utilizan.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-429">The above authentication modes only differ by the supporting tokens they use.</span></span> <span data-ttu-id="2b4e0-430">AnonymousForCertificate no tiene ningún token auxiliar, MutualCertificate WSS 1.1 tiene el certificado X509 de cliente como un token auxiliar de aprobación, UserNameForCertificate tiene un token de nombre de usuario como un token auxiliar firmado e IssuedTokenForCertificate tiene el token emitido como un token auxiliar de aprobación.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-430">AnonymousForCertificate does not have any supporting tokens, MutualCertificate WSS 1.1 has the client’s X509 certificate as an endorsing supporting tokens, UserNameForCertificate has a UserName Token as a signed supporting token and IssuedTokenForCertificate has the issued token as an endorsing supporting token.</span></span>  
  
 <span data-ttu-id="2b4e0-431">Directiva</span><span class="sxs-lookup"><span data-stu-id="2b4e0-431">Policy</span></span>  
  
 <span data-ttu-id="2b4e0-432">Enlace simétrico</span><span class="sxs-lookup"><span data-stu-id="2b4e0-432">Symmetric Binding</span></span>  
  
```xml  
<wsp:Policy wsu:Id='SymmetricCert_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:SymmetricBinding>  
        <wsp:Policy>  
          <sp:ProtectionToken>  
            <wsp:Policy>  
              <sp:X509Token   
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/Never' >  
                <wsp:Policy>  
                  <sp:RequireDerivedKeys />   
                  <sp:RequireThumbprintReference />   
                  <sp:WssX509V3Token10 />   
                </wsp:Policy>  
              </sp:X509Token>  
            </wsp:Policy>  
          </sp:ProtectionToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />   
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />   
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />   
          <sp:EncryptSignature />   
          <sp:OnlySignEntireHeadersAndBody />  
        </wsp:Policy>  
      </sp:SymmetricBinding>  
      <!-- Supporting Token Assertions appear here -->  
      ...  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />   
          <sp:MustSupportRefIssuerSerial />   
          <sp:MustSupportRefThumbprint />   
          <sp:MustSupportRefEncryptedKey />   
          <sp:RequireSignatureConfirmation />   
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />   
          <sp:RequireClientEntropy />   
          <sp:RequireServerEntropy />   
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />   
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
#### <a name="624-anonymousforcertificate"></a><span data-ttu-id="2b4e0-433">6.2.4 AnonymousForCertificate</span><span class="sxs-lookup"><span data-stu-id="2b4e0-433">6.2.4 AnonymousForCertificate</span></span>  
 <span data-ttu-id="2b4e0-434">Con este modo de autenticación, el cliente es anónimo y el servicio se autentica utilizando un certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-434">With this authentication mode the client is anonymous and the service is authenticated using an X.509 certificate.</span></span> <span data-ttu-id="2b4e0-435">El enlace utilizado es una instancia de enlace simétrico tal y como se describe en 6.4.2.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-435">The binding used is an instance of symmetric binding as described in 6.4.2.</span></span>  
  
 <span data-ttu-id="2b4e0-436">Directiva</span><span class="sxs-lookup"><span data-stu-id="2b4e0-436">Policy</span></span>  
  
 <span data-ttu-id="2b4e0-437">Vea "Directiva" en 6.2.3 más arriba para obtener detalles sobre enlaces</span><span class="sxs-lookup"><span data-stu-id="2b4e0-437">See "Policy" in 6.2.3 above for binding details</span></span>  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="2b4e0-438">Ejemplos de encabezado de seguridad: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="2b4e0-438">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="2b4e0-439">Request</span><span class="sxs-lookup"><span data-stu-id="2b4e0-439">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="2b4e0-440">Respuesta</span><span class="sxs-lookup"><span data-stu-id="2b4e0-440">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="2b4e0-441">Ejemplos de encabezado de seguridad: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="2b4e0-441">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="2b4e0-442">Request</span><span class="sxs-lookup"><span data-stu-id="2b4e0-442">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="2b4e0-443">Respuesta</span><span class="sxs-lookup"><span data-stu-id="2b4e0-443">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wsse11:SignatureConfirmation />  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="625-usernameforcertificate"></a><span data-ttu-id="2b4e0-444">6.2.5 UserNameForCertificate</span><span class="sxs-lookup"><span data-stu-id="2b4e0-444">6.2.5 UserNameForCertificate</span></span>  
 <span data-ttu-id="2b4e0-445">Con este modo de autenticación el cliente se autentica en el servicio utilizando un token de nombre de usuario que aparece en la capa SOAP como un token auxiliar firmado.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-445">With this authentication mode the client authenticates to the service using a Username Token which appears at the SOAP layer as a signed supporting token.</span></span> <span data-ttu-id="2b4e0-446">El servicio autentica al cliente utilizando un certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-446">The service authenticates to the client using an X.509 certificate.</span></span> <span data-ttu-id="2b4e0-447">El enlace utilizado es un enlace simétrico donde el token de protección es una clave generada por el cliente, cifrada con la clave pública del servicio.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-447">The binding used is a symmetric binding with the protection token being a key generated by the client, encrypted with the public key of the service.</span></span>  
  
 <span data-ttu-id="2b4e0-448">Directiva</span><span class="sxs-lookup"><span data-stu-id="2b4e0-448">Policy</span></span>  
  
 <span data-ttu-id="2b4e0-449">Vea "Directiva" en 6.2.3 más arriba para obtener detalles sobre enlaces</span><span class="sxs-lookup"><span data-stu-id="2b4e0-449">See "Policy" in 6.2.3 above for binding details</span></span>  
  
 <span data-ttu-id="2b4e0-450">Token auxiliar firmado</span><span class="sxs-lookup"><span data-stu-id="2b4e0-450">Signed Supporting Token</span></span>  
  
```xml  
<sp:SignedSupportingTokens>  
  <wsp:Policy>  
    <sp:UsernameToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
      <wsp:Policy>  
        <sp:WssUsernameToken10 />   
      </wsp:Policy>  
    </sp:UsernameToken>  
  </wsp:Policy>  
</sp:SignedSupportingTokens>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="2b4e0-451">Ejemplos de encabezado de seguridad: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="2b4e0-451">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="2b4e0-452">Request</span><span class="sxs-lookup"><span data-stu-id="2b4e0-452">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="2b4e0-453">Respuesta</span><span class="sxs-lookup"><span data-stu-id="2b4e0-453">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="2b4e0-454">Ejemplos de encabezado de seguridad: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="2b4e0-454">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="2b4e0-455">Request</span><span class="sxs-lookup"><span data-stu-id="2b4e0-455">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="2b4e0-456">Respuesta</span><span class="sxs-lookup"><span data-stu-id="2b4e0-456">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="626-mutualcertificate-wss-11"></a><span data-ttu-id="2b4e0-457">6.2.6 MutualCertificate (WSS 1.1)</span><span class="sxs-lookup"><span data-stu-id="2b4e0-457">6.2.6 MutualCertificate (WSS 1.1)</span></span>  
 <span data-ttu-id="2b4e0-458">Con este modo de autenticación el cliente se autentica mediante un certificado X.509 que aparece en la capa SOAP como el token auxiliar de aprobación.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-458">With this authentication mode the client authenticates using an X.509 certificate which appears at the SOAP layer as an endorsing supporting token.</span></span> <span data-ttu-id="2b4e0-459">La autenticación del servicio también se realiza mediante un certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-459">The service is also authenticated using an X.509 certificate.</span></span> <span data-ttu-id="2b4e0-460">El enlace utilizado es un enlace simétrico donde el token de protección es una clave generada por el cliente, cifrada con la clave pública del servicio.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-460">The binding used is a symmetric binding with the protection token being a key generated by the client, encrypted with the public key of the service.</span></span>  
  
 <span data-ttu-id="2b4e0-461">Directiva</span><span class="sxs-lookup"><span data-stu-id="2b4e0-461">Policy</span></span>  
  
 <span data-ttu-id="2b4e0-462">Vea Directiva en 6.2.3 para obtener detalles sobre enlaces</span><span class="sxs-lookup"><span data-stu-id="2b4e0-462">See Policy in 6.2.3 for binding details</span></span>  
  
 <span data-ttu-id="2b4e0-463">Aprobar token auxiliar</span><span class="sxs-lookup"><span data-stu-id="2b4e0-463">Endorsing Supporting Token</span></span>  
  
```xml  
<sp:EndorsingSupportingTokens>  
  <wsp:Policy>  
    <sp:X509Token sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
      <wsp:Policy>  
        <sp:RequireThumbprintReference />   
        <sp:WssX509V3Token10 />   
      </wsp:Policy>  
    </sp:X509Token>  
  </wsp:Policy>  
</sp:EndorsingSupportingTokens>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="2b4e0-464">Ejemplos de encabezado de seguridad: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="2b4e0-464">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="2b4e0-465">Request</span><span class="sxs-lookup"><span data-stu-id="2b4e0-465">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="2b4e0-466">Respuesta</span><span class="sxs-lookup"><span data-stu-id="2b4e0-466">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="2b4e0-467">Ejemplos de encabezado de seguridad: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="2b4e0-467">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="2b4e0-468">Request</span><span class="sxs-lookup"><span data-stu-id="2b4e0-468">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="2b4e0-469">Respuesta</span><span class="sxs-lookup"><span data-stu-id="2b4e0-469">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wsse11:SignatureConfirmation />  
  <wsse11:SignatureConfirmation />  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="627-issuedtokenforcertificate"></a><span data-ttu-id="2b4e0-470">6.2.7 IssuedTokenForCertificate</span><span class="sxs-lookup"><span data-stu-id="2b4e0-470">6.2.7 IssuedTokenForCertificate</span></span>  
 <span data-ttu-id="2b4e0-471">Con este modo de autenticación, el cliente no se autentica al servicio como tal; sino que, en su lugar, presenta un token emitido por un STS y demuestra que conoce una clave compartida.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-471">With this authentication mode the client does not authenticate to the service, as such, but instead presents a token issued by a STS and proves knowledge of a shared key.</span></span> <span data-ttu-id="2b4e0-472">El token emitido aparece en la capa de SOAP como un token auxiliar de aprobación.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-472">The issued token appears at the SOAP layer as an endorsing supporting token.</span></span> <span data-ttu-id="2b4e0-473">El servicio autentica al cliente utilizando un certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-473">The service authenticates to the client using an X.509 certificate.</span></span> <span data-ttu-id="2b4e0-474">El enlace utilizado es un enlace simétrico donde el token de protección es una clave generada por el cliente, cifrada con la clave pública del servicio.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-474">The binding used is a symmetric binding with the protection token being a key generated by the client, encrypted with the public key of the service.</span></span>  
  
 <span data-ttu-id="2b4e0-475">Directiva</span><span class="sxs-lookup"><span data-stu-id="2b4e0-475">Policy</span></span>  
  
 <span data-ttu-id="2b4e0-476">Vea Directiva en 6.2.3 más arriba para obtener detalles sobre enlaces</span><span class="sxs-lookup"><span data-stu-id="2b4e0-476">See Policy in 6.2.3 above for binding details</span></span>  
  
 <span data-ttu-id="2b4e0-477">Aprobar token auxiliar</span><span class="sxs-lookup"><span data-stu-id="2b4e0-477">Endorsing Supporting Token</span></span>  
  
```xml  
<sp:EndorsingSupportingTokens>  
  <wsp:Policy>  
    <sp:IssuedToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
      <sp:RequestSecurityTokenTemplate>  
        <wst:KeyType>  
http://schemas.xmlsoap.org/ws/2005/02/trust/SymmetricKey  
       </wst:KeyType>  
     </sp:RequestSecurityTokenTemplate>  
     <wsp:Policy>  
       <sp:RequireDerivedKeys />   
       <sp:RequireInternalReference />   
     </wsp:Policy>  
   </sp:IssuedToken>  
  </wsp:Policy>  
</sp:EndorsingSupportingTokens>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="2b4e0-478">Ejemplos de encabezado de seguridad: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="2b4e0-478">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="2b4e0-479">Request</span><span class="sxs-lookup"><span data-stu-id="2b4e0-479">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <saml:Assertion>  
  ...  
  </saml:Assertion>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="2b4e0-480">Respuesta</span><span class="sxs-lookup"><span data-stu-id="2b4e0-480">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="2b4e0-481">Ejemplos de encabezado de seguridad: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="2b4e0-481">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="2b4e0-482">Request</span><span class="sxs-lookup"><span data-stu-id="2b4e0-482">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <saml:Assertion>  
  ...  
  </saml:Assertion>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="2b4e0-483">Respuesta</span><span class="sxs-lookup"><span data-stu-id="2b4e0-483">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wsse11:SignatureConfirmation />  
  <wsse11:SignatureConfirmation />  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
## <a name="63-kerberos"></a><span data-ttu-id="2b4e0-484">6.3 Kerberos</span><span class="sxs-lookup"><span data-stu-id="2b4e0-484">6.3 Kerberos</span></span>  
 <span data-ttu-id="2b4e0-485">Con este modo de autenticación, el cliente se autentica en el servicio utilizando un tique de Kerberos.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-485">With this authentication mode the client authenticates to the service using a Kerberos ticket.</span></span> <span data-ttu-id="2b4e0-486">Ese mismo vale también proporciona autenticación del servidor.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-486">That same ticket also provides server authentication.</span></span> <span data-ttu-id="2b4e0-487">El enlace utilizado es un enlace simétrico con las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="2b4e0-487">The binding used is a symmetric binding with the following properties;</span></span>  
  
 <span data-ttu-id="2b4e0-488">Token de protección: vale de Kerberos, modo de inclusión establecido en .../IncludeToken/Once</span><span class="sxs-lookup"><span data-stu-id="2b4e0-488">Protection Token: Kerberos Ticket, inclusion mode is set to .../IncludeToken/Once</span></span>  
<span data-ttu-id="2b4e0-489">Protección de tokens: False</span><span class="sxs-lookup"><span data-stu-id="2b4e0-489">Token Protection: False</span></span>  
  
 <span data-ttu-id="2b4e0-490">Encabezado completo y firmas de cuerpo: True</span><span class="sxs-lookup"><span data-stu-id="2b4e0-490">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="2b4e0-491">Orden de protección: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="2b4e0-491">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="2b4e0-492">Cifrar firma: True</span><span class="sxs-lookup"><span data-stu-id="2b4e0-492">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="2b4e0-493">Directiva</span><span class="sxs-lookup"><span data-stu-id="2b4e0-493">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='Kerberos_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:SymmetricBinding>  
        <wsp:Policy>  
          <sp:ProtectionToken>  
            <wsp:Policy>  
              <sp:KerberosToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/Once' >  
                <wsp:Policy>  
                  <sp:RequireDerivedKeys />   
                  <sp:WssGssKerberosV5ApReqToken11 />   
                </wsp:Policy>  
              </sp:KerberosToken>  
            </wsp:Policy>  
          </sp:ProtectionToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic128 />   
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />   
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />   
          <sp:EncryptSignature />   
          <sp:OnlySignEntireHeadersAndBody />   
        </wsp:Policy>  
      </sp:SymmetricBinding>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />   
          <sp:MustSupportRefIssuerSerial />   
          <sp:MustSupportRefThumbprint />   
          <sp:MustSupportRefEncryptedKey />   
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />   
          <sp:RequireClientEntropy />   
          <sp:RequireServerEntropy />   
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />   
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="2b4e0-494">Ejemplos de encabezado de seguridad: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="2b4e0-494">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="2b4e0-495">Request</span><span class="sxs-lookup"><span data-stu-id="2b4e0-495">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="2b4e0-496">Respuesta</span><span class="sxs-lookup"><span data-stu-id="2b4e0-496">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>    
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="2b4e0-497">Ejemplos de encabezado de seguridad: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="2b4e0-497">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="2b4e0-498">Request</span><span class="sxs-lookup"><span data-stu-id="2b4e0-498">Request</span></span>  
  
```xml  
<wsse:Security>  
TBD  
</wsse:Security>  
```  
  
 <span data-ttu-id="2b4e0-499">Respuesta</span><span class="sxs-lookup"><span data-stu-id="2b4e0-499">Response</span></span>  
  
```xml  
<wsse:Security>  
TBD  
</wsse:Security>  
```  
  
#### <a name="64-issuedtoken"></a><span data-ttu-id="2b4e0-500">6.4 IssuedToken</span><span class="sxs-lookup"><span data-stu-id="2b4e0-500">6.4 IssuedToken</span></span>  
 <span data-ttu-id="2b4e0-501">Con este modo de autenticación, el cliente no se autentica en el servicio como tal; sino que, en su lugar, presenta un token emitido por un STS y demuestra que conoce una clave compartida.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-501">With this authentication mode the client does not authenticate to the service, as such, rather the client presents a token issued by an STS and proves knowledge of a shared key.</span></span> <span data-ttu-id="2b4e0-502">El servicio no se autentica al cliente como tal, sino que, en su lugar, el STS cifra la clave compartida como parte del token emitido, de manera que solo el servicio puede descifrar la clave.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-502">The service is not authenticated to the client, as such, instead the STS encrypts the shared key as part of the issued token such that only the service can decrypt the key.</span></span> <span data-ttu-id="2b4e0-503">El enlace utilizado es un enlace simétrico con las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="2b4e0-503">The binding used is as symmetric binding with the following properties;</span></span>  
  
 <span data-ttu-id="2b4e0-504">Token de protección: token emitido, modo de inclusión establecido en .../IncludeToken/AlwaysToRecipient</span><span class="sxs-lookup"><span data-stu-id="2b4e0-504">Protection Token: Issued Token, inclusion mode is set to .../IncludeToken/AlwaysToRecipient</span></span>  
<span data-ttu-id="2b4e0-505">Protección de tokens: False</span><span class="sxs-lookup"><span data-stu-id="2b4e0-505">Token Protection: False</span></span>  
  
 <span data-ttu-id="2b4e0-506">Encabezado completo y firmas de cuerpo: True</span><span class="sxs-lookup"><span data-stu-id="2b4e0-506">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="2b4e0-507">Orden de protección: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="2b4e0-507">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="2b4e0-508">Cifrar firma: True</span><span class="sxs-lookup"><span data-stu-id="2b4e0-508">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="2b4e0-509">Directiva</span><span class="sxs-lookup"><span data-stu-id="2b4e0-509">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='CustomBinding_ISimple3_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:SymmetricBinding>  
        <wsp:Policy>  
          <sp:ProtectionToken>  
            <wsp:Policy>  
              <sp:IssuedToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
                <sp:RequestSecurityTokenTemplate>  
                  <wst:KeyType>  
http://schemas.xmlsoap.org/ws/2005/02/trust/SymmetricKey  
                  </wst:KeyType>   
                </sp:RequestSecurityTokenTemplate>  
                <wsp:Policy>  
                  <sp:RequireDerivedKeys />   
                  <sp:RequireInternalReference />   
                </wsp:Policy>  
              </sp:IssuedToken>  
            </wsp:Policy>  
          </sp:ProtectionToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />   
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />   
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />   
          <sp:EncryptSignature />   
          <sp:OnlySignEntireHeadersAndBody />   
        </wsp:Policy>  
      </sp:SymmetricBinding>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />   
          <sp:MustSupportRefIssuerSerial />   
          <sp:MustSupportRefThumbprint />   
          <sp:MustSupportRefEncryptedKey />   
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />   
          <sp:RequireClientEntropy />   
          <sp:RequireServerEntropy />   
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />   
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="2b4e0-510">Ejemplos de encabezado de seguridad: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="2b4e0-510">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="2b4e0-511">Request</span><span class="sxs-lookup"><span data-stu-id="2b4e0-511">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <saml:Assertion>  
  ...  
  </saml:Assertion>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="2b4e0-512">Respuesta</span><span class="sxs-lookup"><span data-stu-id="2b4e0-512">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>    
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="2b4e0-513">Ejemplos de encabezado de seguridad: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="2b4e0-513">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="2b4e0-514">Request</span><span class="sxs-lookup"><span data-stu-id="2b4e0-514">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <saml:Assertion>  
  ...  
  </saml:Assertion>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="2b4e0-515">Respuesta</span><span class="sxs-lookup"><span data-stu-id="2b4e0-515">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
### <a name="65-using-sslnegotiated-for-service-authentication"></a><span data-ttu-id="2b4e0-516">6.5 Uso de SslNegotiated para la autenticación de servicio</span><span class="sxs-lookup"><span data-stu-id="2b4e0-516">6.5 Using SslNegotiated for Service Authentication</span></span>  
 <span data-ttu-id="2b4e0-517">En esta sección se describe un grupo de modos de autenticación que utilizan un enlace simétrico donde el token de protección es un token de contexto de seguridad por WS-SecureConversation (WS SC), cuyo valor de clave se negocia ejecutando el protocolo TLS sobre mensajes de RST/RSTR de WS-Trust (WS-T).</span><span class="sxs-lookup"><span data-stu-id="2b4e0-517">This section describes a group of authentication modes that use a symmetric binding with the protection token being a Security Context Token per WS-SecureConversation (WS-SC) whose key value is negotiated by executing the TLS protocol over WS-Trust (WS-T) RST/RSTR messages.</span></span> <span data-ttu-id="2b4e0-518">En TLSNEGO se describen los detalles de la implementación del protocolo de enlace de TLS mediante WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-518">Details of the TLS handshake implementation using WS-Trust are described in TLSNEGO.</span></span> <span data-ttu-id="2b4e0-519">Aquí en los ejemplos de mensajes supondremos que SCT con un contexto de seguridad asociado ya se establece a través de un protocolo de enlace.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-519">Here in the message examples we will assume that SCT with an associated security context is already established through a handshake.</span></span>  
  
 <span data-ttu-id="2b4e0-520">El enlace utilizado es un enlace simétrico con las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="2b4e0-520">The binding used is a symmetric binding with the following properties;</span></span>  
  
 <span data-ttu-id="2b4e0-521">Token de protección: SslContextToken, modo de inclusión establecido en .../IncludeToken/Never</span><span class="sxs-lookup"><span data-stu-id="2b4e0-521">Protection Token: SslContextToken, inclusion mode is set to .../IncludeToken/Never</span></span>  
<span data-ttu-id="2b4e0-522">Protección de tokens: False</span><span class="sxs-lookup"><span data-stu-id="2b4e0-522">Token Protection: False</span></span>  
  
 <span data-ttu-id="2b4e0-523">Encabezado completo y firmas de cuerpo: True</span><span class="sxs-lookup"><span data-stu-id="2b4e0-523">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="2b4e0-524">Orden de protección: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="2b4e0-524">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="2b4e0-525">Cifrar firma: True</span><span class="sxs-lookup"><span data-stu-id="2b4e0-525">Encrypt Signature: True</span></span>  
  
#### <a name="651-policy-for-sslnegotiated-service-authentication"></a><span data-ttu-id="2b4e0-526">6.5.1 Directiva para la autenticación de servicio SslNegotiated</span><span class="sxs-lookup"><span data-stu-id="2b4e0-526">6.5.1 Policy for SslNegotiated service authentication</span></span>  
 <span data-ttu-id="2b4e0-527">La directiva para todos los modos de autenticación de esta sección es similar y solo difieren en los tokens auxiliares firmados o aprobados empleados.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-527">Policy for all authentication modes in this section are similar and differ only by specific signed supporting or endorsing tokens used.</span></span>  
  
```xml  
<wsp:Policy wsu:Id='SslNegotiated_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:SymmetricBinding>  
        <wsp:Policy>  
          <sp:ProtectionToken>  
            <wsp:Policy>  
              <mssp:SslContextToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' />  
                <wsp:Policy>  
                  <sp:RequireDerivedKeys />   
                </wsp:Policy>  
              </mssp:SslContextToken>  
            </wsp:Policy>  
          </sp:ProtectionToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />   
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />   
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />   
          <sp:EncryptSignature />   
          <sp:OnlySignEntireHeadersAndBody />   
        </wsp:Policy>  
      </sp:SymmetricBinding>  
      <!-- Supporting token assertions go here -->  
      ..  
      <sp:Wss11>   
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />   
          <sp:MustSupportRefIssuerSerial />   
          <sp:MustSupportRefThumbprint />   
          <sp:MustSupportRefEncryptedKey />   
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />   
          <sp:RequireClientEntropy />   
          <sp:RequireServerEntropy />   
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />   
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
#### <a name="652-anonymousforsslnegotiated"></a><span data-ttu-id="2b4e0-528">6.5.2 AnonymousForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="2b4e0-528">6.5.2 AnonymousForSslNegotiated</span></span>  
 <span data-ttu-id="2b4e0-529">Con este modo de autenticación, el cliente es anónimo y el servicio se autentica utilizando un certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-529">With this authentication mode the client is anonymous and the service is authenticated using an X.509 certificate.</span></span> <span data-ttu-id="2b4e0-530">El enlace utilizado es una instancia de enlace simétrico tal y como se describe en 6.5.1 más arriba.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-530">The binding used is an instance of symmetric binding as described in 6.5.1 above.</span></span>  
  
 <span data-ttu-id="2b4e0-531">Directiva</span><span class="sxs-lookup"><span data-stu-id="2b4e0-531">Policy</span></span>  
  
 <span data-ttu-id="2b4e0-532">Vea Directiva en 6.5.1 más arriba para obtener detalles sobre enlaces.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-532">See Policy in 6.5.1 above for binding details.</span></span>  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="2b4e0-533">Ejemplos de encabezado de seguridad: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="2b4e0-533">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="2b4e0-534">Request</span><span class="sxs-lookup"><span data-stu-id="2b4e0-534">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="2b4e0-535">Respuesta</span><span class="sxs-lookup"><span data-stu-id="2b4e0-535">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>    
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="2b4e0-536">Ejemplos de encabezado de seguridad: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="2b4e0-536">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="2b4e0-537">Request</span><span class="sxs-lookup"><span data-stu-id="2b4e0-537">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="2b4e0-538">Respuesta</span><span class="sxs-lookup"><span data-stu-id="2b4e0-538">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="653-usernameforsslnegotiated"></a><span data-ttu-id="2b4e0-539">6.5.3 UserNameForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="2b4e0-539">6.5.3 UserNameForSslNegotiated</span></span>  
 <span data-ttu-id="2b4e0-540">Con este modo de autenticación el cliente se autentica el servicio utilizando un token de nombre de usuario que aparece en la capa SOAP como un token auxiliar firmado.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-540">With this authentication mode the client is authenticates using a Username Token which appears at the SOAP layer as a signed supporting token.</span></span> <span data-ttu-id="2b4e0-541">La autenticación del servicio se realiza mediante un certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-541">The service is authenticated using an X.509 certificate.</span></span> <span data-ttu-id="2b4e0-542">El enlace utilizado es una instancia de enlace simétrico tal y como se describe en 6.5.1.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-542">The binding used is an instance of symmetric binding as described in 6.5.1.</span></span>  
  
 <span data-ttu-id="2b4e0-543">Directiva</span><span class="sxs-lookup"><span data-stu-id="2b4e0-543">Policy</span></span>  
  
 <span data-ttu-id="2b4e0-544">Vea la sección 6.5.1 anterior para obtener detalles sobre los enlaces</span><span class="sxs-lookup"><span data-stu-id="2b4e0-544">See section 6.5.1 above for binding details</span></span>  
  
 <span data-ttu-id="2b4e0-545">Token auxiliar firmado</span><span class="sxs-lookup"><span data-stu-id="2b4e0-545">Signed Supporting Token</span></span>  
  
```xml  
<sp:SignedSupportingTokens>  
  <wsp:Policy>  
    <sp:UsernameToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
      <wsp:Policy>  
        <sp:WssUsernameToken10 />   
      </wsp:Policy>  
    </sp:UsernameToken>  
  </wsp:Policy>  
</sp:SignedSupportingTokens>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="2b4e0-546">Ejemplos de encabezado de seguridad: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="2b4e0-546">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="2b4e0-547">Request</span><span class="sxs-lookup"><span data-stu-id="2b4e0-547">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="2b4e0-548">Respuesta</span><span class="sxs-lookup"><span data-stu-id="2b4e0-548">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>    
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="2b4e0-549">Ejemplos de encabezado de seguridad: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="2b4e0-549">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="2b4e0-550">Request</span><span class="sxs-lookup"><span data-stu-id="2b4e0-550">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="2b4e0-551">Respuesta</span><span class="sxs-lookup"><span data-stu-id="2b4e0-551">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="654-issuedtokenforsslnegotiated"></a><span data-ttu-id="2b4e0-552">6.5.4 IssuedTokenForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="2b4e0-552">6.5.4 IssuedTokenForSslNegotiated</span></span>  
 <span data-ttu-id="2b4e0-553">Con este modo de autenticación, el cliente no se autentica al servicio como tal; sino que, en su lugar, presenta un token emitido por un STS y demuestra que conoce una clave compartida.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-553">With this authentication mode the client does not authenticate to the service, as such, but instead presents a token issued by an STS and proves knowledge of a shared key.</span></span> <span data-ttu-id="2b4e0-554">El token emitido aparece en la capa de SOAP como un token auxiliar de aprobación.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-554">The issued token appears at the SOAP layer as an endorsing supporting token.</span></span> <span data-ttu-id="2b4e0-555">La autenticación del servicio se realiza mediante un certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-555">The service is authenticated using an X.509 certificate.</span></span> <span data-ttu-id="2b4e0-556">El enlace utilizado es una instancia de enlace simétrico tal y como se describe en 6.5.1 más arriba.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-556">The binding used is an instance of symmetric binding as described in 6.5.1 above.</span></span>  
  
 <span data-ttu-id="2b4e0-557">Directiva</span><span class="sxs-lookup"><span data-stu-id="2b4e0-557">Policy</span></span>  
  
 <span data-ttu-id="2b4e0-558">Vea la sección 6.5.1 anterior para obtener detalles sobre los enlaces</span><span class="sxs-lookup"><span data-stu-id="2b4e0-558">See section 6.5.1 above for binding details</span></span>  
  
 <span data-ttu-id="2b4e0-559">Aprobar token auxiliar</span><span class="sxs-lookup"><span data-stu-id="2b4e0-559">Endorsing Supporting Token</span></span>  
  
```xml  
<sp:EndorsingSupportingTokens>  
  <wsp:Policy>  
    <sp:IssuedToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
      <sp:RequestSecurityTokenTemplate>  
        <wst:KeyType>  
http://schemas.xmlsoap.org/ws/2005/02/trust/SymmetricKey  
        </wst:KeyType>   
      </sp:RequestSecurityTokenTemplate>  
      <wsp:Policy>  
        <sp:RequireDerivedKeys />   
        <sp:RequireInternalReference />   
      </wsp:Policy>  
    </sp:IssuedToken>  
  </wsp:Policy>  
</sp:EndorsingSupportingTokens>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="2b4e0-560">Ejemplos de encabezado de seguridad: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="2b4e0-560">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="2b4e0-561">Request</span><span class="sxs-lookup"><span data-stu-id="2b4e0-561">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <saml:Assertion>  
  ...  
  </saml:Assertion>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="2b4e0-562">Respuesta</span><span class="sxs-lookup"><span data-stu-id="2b4e0-562">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>    
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="2b4e0-563">Ejemplos de encabezado de seguridad: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="2b4e0-563">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="2b4e0-564">Request</span><span class="sxs-lookup"><span data-stu-id="2b4e0-564">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <saml:Assertion>  
  ...  
  </saml:Assertion>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="2b4e0-565">Respuesta</span><span class="sxs-lookup"><span data-stu-id="2b4e0-565">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsse11:SignatureConfirmation />  
  <wsse11:SignatureConfirmation />  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="655-mutualsslnegotiated"></a><span data-ttu-id="2b4e0-566">6.5.5 MutualSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="2b4e0-566">6.5.5 MutualSslNegotiated</span></span>  
 <span data-ttu-id="2b4e0-567">Con este modo de autenticación, el cliente y el servicio autentican utilizando los certificados X.509.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-567">With this authentication mode the client and the service authenticate using X.509 certificates.</span></span> <span data-ttu-id="2b4e0-568">El enlace utilizado es una instancia de enlace simétrico tal y como se describe en 6.5.1 más arriba.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-568">The binding used is an instance of symmetric binding as described in 6.5.1 above.</span></span>  
  
 <span data-ttu-id="2b4e0-569">Directiva</span><span class="sxs-lookup"><span data-stu-id="2b4e0-569">Policy</span></span>  
  
 <span data-ttu-id="2b4e0-570">Vea la sección 6.5.1 anterior para obtener detalles sobre los enlaces</span><span class="sxs-lookup"><span data-stu-id="2b4e0-570">See section 6.5.1 above for binding details</span></span>  
  
 <span data-ttu-id="2b4e0-571">Aprobar token auxiliar</span><span class="sxs-lookup"><span data-stu-id="2b4e0-571">Endorsing Supporting Token</span></span>  
  
```xml  
<sp:EndorsingSupportingTokens>  
  <wsp:Policy>  
    <sp:X509Token sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
      <wsp:Policy>  
        <sp:RequireThumbprintReference />   
        <sp:WssX509V3Token10 />   
      </wsp:Policy>  
    </sp:X509Token>  
  </wsp:Policy>  
</sp:EndorsingSupportingTokens>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="2b4e0-572">Ejemplos de encabezado de seguridad: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="2b4e0-572">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="2b4e0-573">Request</span><span class="sxs-lookup"><span data-stu-id="2b4e0-573">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="2b4e0-574">Respuesta</span><span class="sxs-lookup"><span data-stu-id="2b4e0-574">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>    
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="2b4e0-575">Ejemplos de encabezado de seguridad: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="2b4e0-575">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="2b4e0-576">Request</span><span class="sxs-lookup"><span data-stu-id="2b4e0-576">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="2b4e0-577">Respuesta</span><span class="sxs-lookup"><span data-stu-id="2b4e0-577">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
### <a name="66-sspinegotiated"></a><span data-ttu-id="2b4e0-578">6.6 SspiNegotiated</span><span class="sxs-lookup"><span data-stu-id="2b4e0-578">6.6 SspiNegotiated</span></span>  
 <span data-ttu-id="2b4e0-579">Con este modo de autenticación, se usa un protocolo de negociación para realizar la autenticación del cliente y del servidor.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-579">With this authentication mode a negotiation protocol is used to perform client and server authentication.</span></span> <span data-ttu-id="2b4e0-580">Se utiliza Kerberos si es posible; de lo contrario, se utiliza NTLM.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-580">Kerberos is used if possible, otherwise NTLM.</span></span> <span data-ttu-id="2b4e0-581">El enlace utilizado es un enlace simétrico con las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="2b4e0-581">The binding used is a symmetric binding with the following properties;</span></span>  
  
 <span data-ttu-id="2b4e0-582">Token de protección: SpnegoContextToken, modo de inclusión establecido en .../IncludeToken/AlwaysToRecipient</span><span class="sxs-lookup"><span data-stu-id="2b4e0-582">Protection Token: SpnegoContextToken, inclusion mode is set to .../IncludeToken/AlwaysToRecipient</span></span>  
<span data-ttu-id="2b4e0-583">Protección de tokens: False</span><span class="sxs-lookup"><span data-stu-id="2b4e0-583">Token Protection: False</span></span>  
  
 <span data-ttu-id="2b4e0-584">Encabezado completo y firmas de cuerpo: True</span><span class="sxs-lookup"><span data-stu-id="2b4e0-584">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="2b4e0-585">Orden de protección: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="2b4e0-585">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="2b4e0-586">Cifrar firma: True</span><span class="sxs-lookup"><span data-stu-id="2b4e0-586">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="2b4e0-587">Directiva</span><span class="sxs-lookup"><span data-stu-id="2b4e0-587">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='CustomBinding_ISimple13_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:SymmetricBinding>  
        <wsp:Policy>  
          <sp:ProtectionToken>  
            <wsp:Policy>  
              <sp:SpnegoContextToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
                <wsp:Policy>  
                  <sp:RequireDerivedKeys />   
                </wsp:Policy>  
              </sp:SpnegoContextToken>  
            </wsp:Policy>  
          </sp:ProtectionToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />   
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />   
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />   
          <sp:EncryptSignature />   
          <sp:OnlySignEntireHeadersAndBody />   
        </wsp:Policy>  
      </sp:SymmetricBinding>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />   
          <sp:MustSupportRefIssuerSerial />   
          <sp:MustSupportRefThumbprint />   
          <sp:MustSupportRefEncryptedKey />   
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />   
          <sp:RequireClientEntropy />   
          <sp:RequireServerEntropy />   
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />   
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="2b4e0-588">Ejemplos de encabezado de seguridad: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="2b4e0-588">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="2b4e0-589">Request</span><span class="sxs-lookup"><span data-stu-id="2b4e0-589">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="2b4e0-590">Respuesta</span><span class="sxs-lookup"><span data-stu-id="2b4e0-590">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>    
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="2b4e0-591">Ejemplos de encabezado de seguridad: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="2b4e0-591">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="2b4e0-592">Request</span><span class="sxs-lookup"><span data-stu-id="2b4e0-592">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="2b4e0-593">Respuesta</span><span class="sxs-lookup"><span data-stu-id="2b4e0-593">Response</span></span>  
  
```xml  
<wsse:Security>  
<wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
### <a name="67-secureconversation"></a><span data-ttu-id="2b4e0-594">6.7 SecureConversation</span><span class="sxs-lookup"><span data-stu-id="2b4e0-594">6.7 SecureConversation</span></span>  
 <span data-ttu-id="2b4e0-595">El enlace utilizado es un enlace simétrico donde el token de protección es un SCT por WS-SecureConversation (WS SC).</span><span class="sxs-lookup"><span data-stu-id="2b4e0-595">The binding used is a symmetric binding with the protection token being a SCT per WS-SecureConversation (WS-SC).</span></span> <span data-ttu-id="2b4e0-596">El SCT se negocia mediante WS-Trust (WS-Trust) o WS-SecureConversation (WS-SC) según un enlace anidado, que es en sí mismo un enlace simétrico que usa un protocolo de negociación.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-596">The SCT is negotiated using WS-Trust (WS-Trust) or WS-SecureConversation (WS-SC) according to a nested binding, which is itself a symmetric binding that uses a negotiation protocol.</span></span> <span data-ttu-id="2b4e0-597">El protocolo de negociación utilizará Kerberos para realizar la autenticación de cliente y servidor si es posible.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-597">The negotiation protocol will use Kerberos to perform client and server authentication if possible.</span></span> <span data-ttu-id="2b4e0-598">Si no se puede utilizar Kerberos, se volverá a NTLM.</span><span class="sxs-lookup"><span data-stu-id="2b4e0-598">If Kerberos cannot be used, it will fall back to NTLM.</span></span>  
  
 <span data-ttu-id="2b4e0-599">Directiva</span><span class="sxs-lookup"><span data-stu-id="2b4e0-599">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='SecureConversation_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:SymmetricBinding>  
        <wsp:Policy>  
          <sp:ProtectionToken>  
            <wsp:Policy>  
              <sp:SecureConversationToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
                <wsp:Policy>  
                  <sp:RequireDerivedKeys />   
                  <sp:BootstrapPolicy>  
                    <wsp:Policy>  
                      <sp:SignedParts>  
                        <sp:Body />   
                        <sp:Header Name='To' Namespace='http://www.w3.org/2005/08/addressing' />   
                        <sp:Header Name='From' Namespace='http://www.w3.org/2005/08/addressing' />   
                        <sp:Header Name='FaultTo' Namespace='http://www.w3.org/2005/08/addressing' />   
                        <sp:Header Name='ReplyTo' Namespace='http://www.w3.org/2005/08/addressing' />   
                        <sp:Header Name='MessageID' Namespace='http://www.w3.org/2005/08/addressing' />   
                        <sp:Header Name='RelatesTo' Namespace='http://www.w3.org/2005/08/addressing' />   
                        <sp:Header Name='Action' Namespace='http://www.w3.org/2005/08/addressing' />   
                      </sp:SignedParts>  
                      <sp:EncryptedParts>  
                        <sp:Body />   
                      </sp:EncryptedParts>  
                      <sp:SymmetricBinding>  
                        <wsp:Policy>  
                          <sp:ProtectionToken>  
                            <wsp:Policy>  
                              <sp:SpnegoContextToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
                                <wsp:Policy>  
                                  <sp:RequireDerivedKeys />   
                                </wsp:Policy>  
                              </sp:SpnegoContextToken>  
                            </wsp:Policy>  
                          </sp:ProtectionToken>  
                          <sp:AlgorithmSuite>  
                            <wsp:Policy>  
                              <sp:Basic256 />   
                            </wsp:Policy>  
                          </sp:AlgorithmSuite>  
                          <sp:Layout>  
                            <wsp:Policy>  
                              <sp:Strict />   
                            </wsp:Policy>  
                          </sp:Layout>  
                          <sp:IncludeTimestamp />   
                          <sp:EncryptSignature />   
                          <sp:OnlySignEntireHeadersAndBody />   
                        </wsp:Policy>  
                      </sp:SymmetricBinding>  
                      <sp:Wss11>  
                        <wsp:Policy>  
                          <sp:MustSupportRefKeyIdentifier />   
                          <sp:MustSupportRefIssuerSerial />   
                          <sp:MustSupportRefThumbprint />   
                          <sp:MustSupportRefEncryptedKey />   
                        </wsp:Policy>  
                      </sp:Wss11>  
                      <sp:Trust10>  
                        <wsp:Policy>  
                          <sp:MustSupportIssuedTokens />   
                          <sp:RequireClientEntropy />   
                          <sp:RequireServerEntropy />   
                        </wsp:Policy>  
                      </sp:Trust10>  
                    </wsp:Policy>  
                  </sp:BootstrapPolicy>  
                </wsp:Policy>  
              </sp:SecureConversationToken>  
            </wsp:Policy>  
          </sp:ProtectionToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />   
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />   
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />   
          <sp:EncryptSignature />   
          <sp:OnlySignEntireHeadersAndBody />   
        </wsp:Policy>  
      </sp:SymmetricBinding>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />   
          <sp:MustSupportRefIssuerSerial />   
          <sp:MustSupportRefThumbprint />   
          <sp:MustSupportRefEncryptedKey />   
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />   
          <sp:RequireClientEntropy />   
          <sp:RequireServerEntropy />   
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />   
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="2b4e0-600">Ejemplos de encabezado de seguridad: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="2b4e0-600">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="2b4e0-601">Request</span><span class="sxs-lookup"><span data-stu-id="2b4e0-601">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="2b4e0-602">Respuesta</span><span class="sxs-lookup"><span data-stu-id="2b4e0-602">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>    
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="2b4e0-603">Ejemplos de encabezado de seguridad: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="2b4e0-603">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="2b4e0-604">Request</span><span class="sxs-lookup"><span data-stu-id="2b4e0-604">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="2b4e0-605">Respuesta</span><span class="sxs-lookup"><span data-stu-id="2b4e0-605">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```
