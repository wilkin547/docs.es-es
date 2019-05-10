---
title: Protocolos de seguridad versión 1.0
ms.date: 03/30/2017
ms.assetid: ee3402d2-1076-410b-a3cb-fae0372bd7af
ms.openlocfilehash: 8114183109befcb77c3bf2b35fe246118da5afde
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64586885"
---
# <a name="security-protocols-version-10"></a><span data-ttu-id="4f13d-102">Protocolos de seguridad versión 1.0</span><span class="sxs-lookup"><span data-stu-id="4f13d-102">Security Protocols version 1.0</span></span>
<span data-ttu-id="4f13d-103">Los protocolos de seguridad de servicios Web proporcionan mecanismos de seguridad de servicios Web que cubren todos los requisitos de seguridad de mensajería para empresas existentes.</span><span class="sxs-lookup"><span data-stu-id="4f13d-103">The Web Services Security Protocols provide Web services security mechanisms that cover all existing enterprise messaging security requirements.</span></span> <span data-ttu-id="4f13d-104">En esta sección se describe los detalles de la versión 1.0 de Windows Communication Foundation (WCF) (implementado en el <xref:System.ServiceModel.Channels.SecurityBindingElement>) para los siguiente servicios Web protocolos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="4f13d-104">This section describes the Windows Communication Foundation (WCF) version 1.0 details (implemented in the <xref:System.ServiceModel.Channels.SecurityBindingElement>) for the following Web services security protocols.</span></span>  
  
|<span data-ttu-id="4f13d-105">Especificación/documento</span><span class="sxs-lookup"><span data-stu-id="4f13d-105">Specification/Document</span></span>|<span data-ttu-id="4f13d-106">Link</span><span class="sxs-lookup"><span data-stu-id="4f13d-106">Link</span></span>|  
|-|-|  
|<span data-ttu-id="4f13d-107">WSS: Seguridad del mensaje SOAP 1.0</span><span class="sxs-lookup"><span data-stu-id="4f13d-107">WSS: SOAP Message Security 1.0</span></span>|<https://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-soap-message-security-1.0.pdf>|
|<span data-ttu-id="4f13d-108">WSS: Perfil 1.0 de Token de nombre de usuario</span><span class="sxs-lookup"><span data-stu-id="4f13d-108">WSS: Username Token Profile 1.0</span></span>|<https://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-username-token-profile-1.0.pdf>|
|<span data-ttu-id="4f13d-109">WSS: X509 token Profile 1.0</span><span class="sxs-lookup"><span data-stu-id="4f13d-109">WSS: X509 Token Profile 1.0</span></span>|<https://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-x509-token-profile-1.0.pdf>|
|<span data-ttu-id="4f13d-110">WSS: 1.1 de SAML Token Profile 1.0</span><span class="sxs-lookup"><span data-stu-id="4f13d-110">WSS: SAML 1.1 Token Profile 1.0</span></span>|<https://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.0.pdf>|
|<span data-ttu-id="4f13d-111">WSS: Seguridad de los mensajes SOAP 1.1</span><span class="sxs-lookup"><span data-stu-id="4f13d-111">WSS: SOAP Message Security 1.1</span></span>|<https://www.oasis-open.org/committees/download.php/16790/wss-v1.1-spec-os-SOAPMessageSecurity.pdf>|
|<span data-ttu-id="4f13d-112">WSS: Token Profile 1.1 de Username</span><span class="sxs-lookup"><span data-stu-id="4f13d-112">WSS Username Token Profile 1.1</span></span>|<https://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-username-token-profile-1.0.pdf>|
|<span data-ttu-id="4f13d-113">WSS: Perfil de Token X.509 1.1</span><span class="sxs-lookup"><span data-stu-id="4f13d-113">WSS: X.509 Token Profile 1.1</span></span>|<https://www.oasis-open.org/committees/download.php/16785/wss-v1.1-spec-os-x509TokenProfile.pdf>|
|<span data-ttu-id="4f13d-114">WSS: Kerberos Token Profile 1.1</span><span class="sxs-lookup"><span data-stu-id="4f13d-114">WSS: Kerberos Token Profile 1.1</span></span>|<https://www.oasis-open.org/committees/download.php/16788/wss-v1.1-spec-os-KerberosTokenProfile.pdf>|
|<span data-ttu-id="4f13d-115">WSS: 1.1 de SAML Token Profile 1.1</span><span class="sxs-lookup"><span data-stu-id="4f13d-115">WSS: SAML 1.1 Token Profile 1.1</span></span>|<https://www.oasis-open.org/committees/download.php/16768/wss-v1.1-spec-os-SAMLTokenProfile.pdf>|
|<span data-ttu-id="4f13d-116">WS-Secure Conversation</span><span class="sxs-lookup"><span data-stu-id="4f13d-116">WS-Secure Conversation</span></span>|<http://specs.xmlsoap.org/ws/2005/02/sc/WS-SecureConversation.pdf>|
|<span data-ttu-id="4f13d-117">WS-Trust</span><span class="sxs-lookup"><span data-stu-id="4f13d-117">WS-Trust</span></span>|<http://specs.xmlsoap.org/ws/2005/02/trust/ws-trust.pdf>|
|<span data-ttu-id="4f13d-118">Nota de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="4f13d-118">Application Note:</span></span><br /><br /> <span data-ttu-id="4f13d-119">Uso de WS-Trust para protocolo de enlace TLS</span><span class="sxs-lookup"><span data-stu-id="4f13d-119">Using WS-Trust for TLS Handshake</span></span>|<span data-ttu-id="4f13d-120">Para su publicación</span><span class="sxs-lookup"><span data-stu-id="4f13d-120">To be published</span></span>|  
|<span data-ttu-id="4f13d-121">Nota de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="4f13d-121">Application Note:</span></span><br /><br /> <span data-ttu-id="4f13d-122">Uso de WS-Trust para SPNEGO</span><span class="sxs-lookup"><span data-stu-id="4f13d-122">Using WS-Trust for SPNEGO</span></span>|<span data-ttu-id="4f13d-123">Para su publicación</span><span class="sxs-lookup"><span data-stu-id="4f13d-123">To be published</span></span>|  
|<span data-ttu-id="4f13d-124">Nota de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="4f13d-124">Application Note:</span></span><br /><br /> <span data-ttu-id="4f13d-125">Referencias e identidad de extremos de direccionamiento de servicios Web</span><span class="sxs-lookup"><span data-stu-id="4f13d-125">Web Services Addressing Endpoint References And Identity</span></span>|<span data-ttu-id="4f13d-126">Para su publicación</span><span class="sxs-lookup"><span data-stu-id="4f13d-126">To be published</span></span>|  
|<span data-ttu-id="4f13d-127">WS-SecurityPolicy 1.1</span><span class="sxs-lookup"><span data-stu-id="4f13d-127">WS-SecurityPolicy 1.1</span></span><br /><br /> <span data-ttu-id="4f13d-128">(2005/07)</span><span class="sxs-lookup"><span data-stu-id="4f13d-128">(2005/07)</span></span>|<http://specs.xmlsoap.org/ws/2005/07/securitypolicy/ws-securitypolicy.pdf><br /><br /> <span data-ttu-id="4f13d-129">modificada por [erratas](https://lists.oasis-open.org/archives/ws-sx/200512/msg00017.html) presentado a OASIS WS-SX Technical Committee</span><span class="sxs-lookup"><span data-stu-id="4f13d-129">as amended by [errata](https://lists.oasis-open.org/archives/ws-sx/200512/msg00017.html) submitted to OASIS WS-SX Technical Committee</span></span> |  
  
 <span data-ttu-id="4f13d-130">WCF, versión 1, proporciona 17 modos de autenticación que se pueden usar como base para la configuración de seguridad de servicios Web.</span><span class="sxs-lookup"><span data-stu-id="4f13d-130">WCF, version 1, provides 17 authentication modes that can be used as the basis for Web services security configuration.</span></span> <span data-ttu-id="4f13d-131">Cada modo se optimiza para un conjunto común de requisitos de implementación, como:</span><span class="sxs-lookup"><span data-stu-id="4f13d-131">Each mode is optimized for a common set of deployment requirements, such as:</span></span>  
  
- <span data-ttu-id="4f13d-132">Credenciales utilizadas para autenticar cliente y servicio.</span><span class="sxs-lookup"><span data-stu-id="4f13d-132">Credentials used to authenticate client and service.</span></span>  
  
- <span data-ttu-id="4f13d-133">Mecanismos de protección de seguridad de transporte o mensaje.</span><span class="sxs-lookup"><span data-stu-id="4f13d-133">Message or transport security protection mechanisms.</span></span>  
  
- <span data-ttu-id="4f13d-134">Patrones de intercambio de mensajes.</span><span class="sxs-lookup"><span data-stu-id="4f13d-134">Message exchange patterns.</span></span>  
  
|<span data-ttu-id="4f13d-135">Modo de autenticación</span><span class="sxs-lookup"><span data-stu-id="4f13d-135">Authentication Mode</span></span>|<span data-ttu-id="4f13d-136">Autenticación del cliente</span><span class="sxs-lookup"><span data-stu-id="4f13d-136">Client Authentication</span></span>|<span data-ttu-id="4f13d-137">Autenticación de servidor</span><span class="sxs-lookup"><span data-stu-id="4f13d-137">Server Authentication</span></span>|<span data-ttu-id="4f13d-138">Modo</span><span class="sxs-lookup"><span data-stu-id="4f13d-138">Mode</span></span>|  
|-------------------------|---------------------------|---------------------------|----------|  
|<span data-ttu-id="4f13d-139">UserNameOverTransport</span><span class="sxs-lookup"><span data-stu-id="4f13d-139">UserNameOverTransport</span></span>|<span data-ttu-id="4f13d-140">Nombre de usuario/contraseña</span><span class="sxs-lookup"><span data-stu-id="4f13d-140">User name/password</span></span>|<span data-ttu-id="4f13d-141">X509</span><span class="sxs-lookup"><span data-stu-id="4f13d-141">X509</span></span>|<span data-ttu-id="4f13d-142">Transporte</span><span class="sxs-lookup"><span data-stu-id="4f13d-142">Transport</span></span>|  
|<span data-ttu-id="4f13d-143">CertificateOverTransport</span><span class="sxs-lookup"><span data-stu-id="4f13d-143">CertificateOverTransport</span></span>|<span data-ttu-id="4f13d-144">X509</span><span class="sxs-lookup"><span data-stu-id="4f13d-144">X509</span></span>|<span data-ttu-id="4f13d-145">X509</span><span class="sxs-lookup"><span data-stu-id="4f13d-145">X509</span></span>|<span data-ttu-id="4f13d-146">Transporte</span><span class="sxs-lookup"><span data-stu-id="4f13d-146">Transport</span></span>|  
|<span data-ttu-id="4f13d-147">KerberosOverTransport</span><span class="sxs-lookup"><span data-stu-id="4f13d-147">KerberosOverTransport</span></span>|<span data-ttu-id="4f13d-148">Windows</span><span class="sxs-lookup"><span data-stu-id="4f13d-148">Windows</span></span>|<span data-ttu-id="4f13d-149">X509</span><span class="sxs-lookup"><span data-stu-id="4f13d-149">X509</span></span>|<span data-ttu-id="4f13d-150">Transporte</span><span class="sxs-lookup"><span data-stu-id="4f13d-150">Transport</span></span>|  
|<span data-ttu-id="4f13d-151">IssuedTokenOverTransport</span><span class="sxs-lookup"><span data-stu-id="4f13d-151">IssuedTokenOverTransport</span></span>|<span data-ttu-id="4f13d-152">Federado</span><span class="sxs-lookup"><span data-stu-id="4f13d-152">Federated</span></span>|<span data-ttu-id="4f13d-153">X509</span><span class="sxs-lookup"><span data-stu-id="4f13d-153">X509</span></span>|<span data-ttu-id="4f13d-154">Transporte</span><span class="sxs-lookup"><span data-stu-id="4f13d-154">Transport</span></span>|  
|<span data-ttu-id="4f13d-155">SspiNegotiatedOverTransport</span><span class="sxs-lookup"><span data-stu-id="4f13d-155">SspiNegotiatedOverTransport</span></span>|<span data-ttu-id="4f13d-156">Windows SSPI negociado</span><span class="sxs-lookup"><span data-stu-id="4f13d-156">Windows Sspi Negotiated</span></span>|<span data-ttu-id="4f13d-157">Windows SSPI negociado</span><span class="sxs-lookup"><span data-stu-id="4f13d-157">Windows Sspi Negotiated</span></span>|<span data-ttu-id="4f13d-158">Transporte</span><span class="sxs-lookup"><span data-stu-id="4f13d-158">Transport</span></span>|  
|<span data-ttu-id="4f13d-159">AnonymousForCertificate</span><span class="sxs-lookup"><span data-stu-id="4f13d-159">AnonymousForCertificate</span></span>|<span data-ttu-id="4f13d-160">Ninguna</span><span class="sxs-lookup"><span data-stu-id="4f13d-160">None</span></span>|<span data-ttu-id="4f13d-161">X509</span><span class="sxs-lookup"><span data-stu-id="4f13d-161">X509</span></span>|<span data-ttu-id="4f13d-162">Mensaje</span><span class="sxs-lookup"><span data-stu-id="4f13d-162">Message</span></span>|  
|<span data-ttu-id="4f13d-163">UserNameForCertificate</span><span class="sxs-lookup"><span data-stu-id="4f13d-163">UserNameForCertificate</span></span>|<span data-ttu-id="4f13d-164">Nombre de usuario/contraseña</span><span class="sxs-lookup"><span data-stu-id="4f13d-164">User name/password</span></span>|<span data-ttu-id="4f13d-165">X509</span><span class="sxs-lookup"><span data-stu-id="4f13d-165">X509</span></span>|<span data-ttu-id="4f13d-166">Mensaje</span><span class="sxs-lookup"><span data-stu-id="4f13d-166">Message</span></span>|  
|<span data-ttu-id="4f13d-167">MutualCertificate</span><span class="sxs-lookup"><span data-stu-id="4f13d-167">MutualCertificate</span></span>|<span data-ttu-id="4f13d-168">X509</span><span class="sxs-lookup"><span data-stu-id="4f13d-168">X509</span></span>|<span data-ttu-id="4f13d-169">X509</span><span class="sxs-lookup"><span data-stu-id="4f13d-169">X509</span></span>|<span data-ttu-id="4f13d-170">Mensaje</span><span class="sxs-lookup"><span data-stu-id="4f13d-170">Message</span></span>|  
|<span data-ttu-id="4f13d-171">MutualCertificateDuplex</span><span class="sxs-lookup"><span data-stu-id="4f13d-171">MutualCertificateDuplex</span></span>|<span data-ttu-id="4f13d-172">X509</span><span class="sxs-lookup"><span data-stu-id="4f13d-172">X509</span></span>|<span data-ttu-id="4f13d-173">X509</span><span class="sxs-lookup"><span data-stu-id="4f13d-173">X509</span></span>|<span data-ttu-id="4f13d-174">Mensaje</span><span class="sxs-lookup"><span data-stu-id="4f13d-174">Message</span></span>|  
|<span data-ttu-id="4f13d-175">IssuedTokenForCertificate</span><span class="sxs-lookup"><span data-stu-id="4f13d-175">IssuedTokenForCertificate</span></span>|<span data-ttu-id="4f13d-176">Federado</span><span class="sxs-lookup"><span data-stu-id="4f13d-176">Federated</span></span>|<span data-ttu-id="4f13d-177">X509</span><span class="sxs-lookup"><span data-stu-id="4f13d-177">X509</span></span>|<span data-ttu-id="4f13d-178">Mensaje</span><span class="sxs-lookup"><span data-stu-id="4f13d-178">Message</span></span>|  
|<span data-ttu-id="4f13d-179">Kerberos</span><span class="sxs-lookup"><span data-stu-id="4f13d-179">Kerberos</span></span>|<span data-ttu-id="4f13d-180">Windows</span><span class="sxs-lookup"><span data-stu-id="4f13d-180">Windows</span></span>|<span data-ttu-id="4f13d-181">Windows</span><span class="sxs-lookup"><span data-stu-id="4f13d-181">Windows</span></span>|<span data-ttu-id="4f13d-182">Mensaje</span><span class="sxs-lookup"><span data-stu-id="4f13d-182">Message</span></span>|  
|<span data-ttu-id="4f13d-183">IssuedToken</span><span class="sxs-lookup"><span data-stu-id="4f13d-183">IssuedToken</span></span>|<span data-ttu-id="4f13d-184">Federado</span><span class="sxs-lookup"><span data-stu-id="4f13d-184">Federated</span></span>|<span data-ttu-id="4f13d-185">Federado</span><span class="sxs-lookup"><span data-stu-id="4f13d-185">Federated</span></span>|<span data-ttu-id="4f13d-186">Mensaje</span><span class="sxs-lookup"><span data-stu-id="4f13d-186">Message</span></span>|  
|<span data-ttu-id="4f13d-187">SspiNegotiated</span><span class="sxs-lookup"><span data-stu-id="4f13d-187">SspiNegotiated</span></span>|<span data-ttu-id="4f13d-188">Windows SSPI negociado</span><span class="sxs-lookup"><span data-stu-id="4f13d-188">Windows Sspi Negotiated</span></span>|<span data-ttu-id="4f13d-189">Windows SSPI negociado</span><span class="sxs-lookup"><span data-stu-id="4f13d-189">Windows Sspi Negotiated</span></span>|<span data-ttu-id="4f13d-190">Mensaje</span><span class="sxs-lookup"><span data-stu-id="4f13d-190">Message</span></span>|  
|<span data-ttu-id="4f13d-191">AnonymousForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="4f13d-191">AnonymousForSslNegotiated</span></span>|<span data-ttu-id="4f13d-192">Ninguna</span><span class="sxs-lookup"><span data-stu-id="4f13d-192">None</span></span>|<span data-ttu-id="4f13d-193">X509, TLS-Nego</span><span class="sxs-lookup"><span data-stu-id="4f13d-193">X509, TLS-Nego</span></span>|<span data-ttu-id="4f13d-194">Mensaje</span><span class="sxs-lookup"><span data-stu-id="4f13d-194">Message</span></span>|  
|<span data-ttu-id="4f13d-195">UserNameForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="4f13d-195">UserNameForSslNegotiated</span></span>|<span data-ttu-id="4f13d-196">Nombre de usuario/contraseña</span><span class="sxs-lookup"><span data-stu-id="4f13d-196">User name/password</span></span>|<span data-ttu-id="4f13d-197">X509, TLS-Nego</span><span class="sxs-lookup"><span data-stu-id="4f13d-197">X509, TLS-Nego</span></span>|<span data-ttu-id="4f13d-198">Mensaje</span><span class="sxs-lookup"><span data-stu-id="4f13d-198">Message</span></span>|  
|<span data-ttu-id="4f13d-199">MutualSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="4f13d-199">MutualSslNegotiated</span></span>|<span data-ttu-id="4f13d-200">X509</span><span class="sxs-lookup"><span data-stu-id="4f13d-200">X509</span></span>|<span data-ttu-id="4f13d-201">X509, TLS-Nego</span><span class="sxs-lookup"><span data-stu-id="4f13d-201">X509, TLS-Nego</span></span>|<span data-ttu-id="4f13d-202">Mensaje</span><span class="sxs-lookup"><span data-stu-id="4f13d-202">Message</span></span>|  
|<span data-ttu-id="4f13d-203">IssuedTokenForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="4f13d-203">IssuedTokenForSslNegotiated</span></span>|<span data-ttu-id="4f13d-204">Federado</span><span class="sxs-lookup"><span data-stu-id="4f13d-204">Federated</span></span>|<span data-ttu-id="4f13d-205">X509, TLS-Nego</span><span class="sxs-lookup"><span data-stu-id="4f13d-205">X509, TLS-Nego</span></span>|<span data-ttu-id="4f13d-206">Mensaje</span><span class="sxs-lookup"><span data-stu-id="4f13d-206">Message</span></span>|  
  
 <span data-ttu-id="4f13d-207">Los extremos que usan tales modos de autenticación pueden expresar sus requisitos de seguridad mediante WS-SecurityPolicy (WS-SP).</span><span class="sxs-lookup"><span data-stu-id="4f13d-207">Endpoints using such authentication modes can express their security requirements using WS-SecurityPolicy (WS-SP).</span></span> <span data-ttu-id="4f13d-208">Este documento describe la estructura de mensajes de infraestructura y encabezado de seguridad para cada modo de autenticación y proporciona ejemplos de directivas y mensajes.</span><span class="sxs-lookup"><span data-stu-id="4f13d-208">This document describes the structure of security header and infrastructure messages for each authentication mode and provides examples of policies and messages.</span></span>  
  
 <span data-ttu-id="4f13d-209">WCF reutiliza WS-SecureConversation para proporcionar compatibilidad con sesiones seguras para proteger los intercambios de múltiples mensajes entre aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="4f13d-209">WCF leverages WS-SecureConversation to provide secure sessions support to protect multi-message exchanges between applications.</span></span>  <span data-ttu-id="4f13d-210">Vea "Sesiones seguras" más abajo para obtener detalles de implementación.</span><span class="sxs-lookup"><span data-stu-id="4f13d-210">See "Secure Sessions" below for implementation details.</span></span>  
  
 <span data-ttu-id="4f13d-211">Además de los modos de autenticación, WCF proporciona opciones para controlar mecanismos de protección comunes que se aplican a la mayoría de los modos de autenticación basada en la seguridad de mensaje, por ejemplo: pedido de firma frente a las operaciones de cifrado, los conjuntos de algoritmos, derivación de claves y la confirmación de firma.</span><span class="sxs-lookup"><span data-stu-id="4f13d-211">In addition to authentication modes, WCF provides settings to control common protection mechanisms that apply to most message security-based authentication modes, for example: order of signature versus encryption operations, algorithm suites, key derivation, and signature confirmation.</span></span>  
  
 <span data-ttu-id="4f13d-212">Los siguientes prefijos y espacios de nombres se utilizan en este documento.</span><span class="sxs-lookup"><span data-stu-id="4f13d-212">The following prefixes and namespaces are used in this document.</span></span>  
  
|<span data-ttu-id="4f13d-213">Prefijo</span><span class="sxs-lookup"><span data-stu-id="4f13d-213">Prefix</span></span>|<span data-ttu-id="4f13d-214">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="4f13d-214">Namespace</span></span>|  
|------------|---------------|  
|<span data-ttu-id="4f13d-215">s</span><span class="sxs-lookup"><span data-stu-id="4f13d-215">s</span></span>|<https://www.w3.org/2003/05/soap-envelope/>|
|<span data-ttu-id="4f13d-216">sp</span><span class="sxs-lookup"><span data-stu-id="4f13d-216">sp</span></span>|<http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/>|
|<span data-ttu-id="4f13d-217">a</span><span class="sxs-lookup"><span data-stu-id="4f13d-217">a</span></span>|<https://www.w3.org/2005/08/addressing>|  
|<span data-ttu-id="4f13d-218">wsse</span><span class="sxs-lookup"><span data-stu-id="4f13d-218">wsse</span></span>|<span data-ttu-id="4f13d-219">TBD – OASIS WSS 1,0 URI</span><span class="sxs-lookup"><span data-stu-id="4f13d-219">TBD – OASIS WSS 1.0 URI</span></span>|  
|<span data-ttu-id="4f13d-220">wsse11</span><span class="sxs-lookup"><span data-stu-id="4f13d-220">wsse11</span></span>|<span data-ttu-id="4f13d-221">TBD – OASIS WSS 1.1 URI</span><span class="sxs-lookup"><span data-stu-id="4f13d-221">TBD – OASIS WSS 1.1 URI</span></span>|  
|<span data-ttu-id="4f13d-222">wsu</span><span class="sxs-lookup"><span data-stu-id="4f13d-222">wsu</span></span>|<span data-ttu-id="4f13d-223">TBD – OASIS WSS 1.0 Utility URI</span><span class="sxs-lookup"><span data-stu-id="4f13d-223">TBD – OASIS WSS 1.0 Utility URI</span></span>|  
|<span data-ttu-id="4f13d-224">ds</span><span class="sxs-lookup"><span data-stu-id="4f13d-224">ds</span></span>|<span data-ttu-id="4f13d-225">TBD – W3C XMLDSig URI</span><span class="sxs-lookup"><span data-stu-id="4f13d-225">TBD – W3C XMLDSig URI</span></span>|  
|<span data-ttu-id="4f13d-226">wst</span><span class="sxs-lookup"><span data-stu-id="4f13d-226">wst</span></span>|<span data-ttu-id="4f13d-227">TBD – WS-Trust 2005/02 URI</span><span class="sxs-lookup"><span data-stu-id="4f13d-227">TBD – WS-Trust 2005/02 URI</span></span>|  
|<span data-ttu-id="4f13d-228">wssc</span><span class="sxs-lookup"><span data-stu-id="4f13d-228">wssc</span></span>|<span data-ttu-id="4f13d-229">TBD – WS-SecureConversation 2005/02 URI</span><span class="sxs-lookup"><span data-stu-id="4f13d-229">TBD – WS-SecureConversation 2005/02 URI</span></span>|  
|<span data-ttu-id="4f13d-230">wsaw</span><span class="sxs-lookup"><span data-stu-id="4f13d-230">wsaw</span></span>|<span data-ttu-id="4f13d-231">TBD - Espacio de nombres de directiva WS-Addressing</span><span class="sxs-lookup"><span data-stu-id="4f13d-231">TBD - WS-Addressing policy namespace</span></span>|  
|<span data-ttu-id="4f13d-232">wsp</span><span class="sxs-lookup"><span data-stu-id="4f13d-232">wsp</span></span>|<http://schemas.xmlsoap.org/ws/2004/09/policy>|  
|<span data-ttu-id="4f13d-233">mssp</span><span class="sxs-lookup"><span data-stu-id="4f13d-233">mssp</span></span>|<http://schemas.xmlsoap.org/ws/2005/07/securitypolicy>|
  
## <a name="1-token-profiles"></a><span data-ttu-id="4f13d-234">1. Perfiles de tokens</span><span class="sxs-lookup"><span data-stu-id="4f13d-234">1. Token Profiles</span></span>  
 <span data-ttu-id="4f13d-235">Las especificaciones Seguridad de Servicios web representan la credencial como tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="4f13d-235">Web Services Security specifications represent credential as security tokens.</span></span> <span data-ttu-id="4f13d-236">WCF admite los siguientes tipos de token:</span><span class="sxs-lookup"><span data-stu-id="4f13d-236">WCF supports the following token types:</span></span>  
  
### <a name="11-usernametoken"></a><span data-ttu-id="4f13d-237">1.1 UsernameToken</span><span class="sxs-lookup"><span data-stu-id="4f13d-237">1.1 UsernameToken</span></span>  
 <span data-ttu-id="4f13d-238">WCF sigue perfiles UsernameToken10 y UsernameToken11 con las siguientes restricciones:</span><span class="sxs-lookup"><span data-stu-id="4f13d-238">WCF follows UsernameToken10 and UsernameToken11 profiles with the following constraints:</span></span>  
  
 <span data-ttu-id="4f13d-239">El atributo R1101 PasswordType en el elemento UsernameToken\Password no se debe omitir ni debe tener el valor #PasswordText (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="4f13d-239">R1101 PasswordType attribute on UsernameToken\Password element MUST be either omitted or have value #PasswordText (default).</span></span>  
  
 <span data-ttu-id="4f13d-240">Uno puede implementar el #PasswordDigest mediante extensibilidad.</span><span class="sxs-lookup"><span data-stu-id="4f13d-240">One can implement the #PasswordDigest using extensibility.</span></span> <span data-ttu-id="4f13d-241">Se ha observado que #PasswordDigest se confunde a menudo como un mecanismo de protección de contraseña suficientemente seguro.</span><span class="sxs-lookup"><span data-stu-id="4f13d-241">It has been observed that #PasswordDigest was often mistaken to be a secure enough password protection mechanism.</span></span> <span data-ttu-id="4f13d-242">Pero #PasswordDigest no puede actuar como un sustituto del cifrado del UsernameToken.</span><span class="sxs-lookup"><span data-stu-id="4f13d-242">But #PasswordDigest cannot serve as a substitute for encryption of the UsernameToken.</span></span> <span data-ttu-id="4f13d-243">El objetivo principal de #PasswordDigest es la protección frente a ataques mediante repetición.</span><span class="sxs-lookup"><span data-stu-id="4f13d-243">The primary goal of #PasswordDigest is protection against replay attacks.</span></span> <span data-ttu-id="4f13d-244">En los modos de autenticación de WCF, mitigar las amenazas de ataques de reproducción mediante el uso de las firmas del mensaje.</span><span class="sxs-lookup"><span data-stu-id="4f13d-244">In WCF authentication modes, replay attack threats are mitigated by using message signatures.</span></span>  
  
 <span data-ttu-id="4f13d-245">WCF B1102 nunca emite subelementos Nonce y Created del UsernameToken.</span><span class="sxs-lookup"><span data-stu-id="4f13d-245">B1102 WCF never emits Nonce and Created sub-elements of the UsernameToken.</span></span>  
  
 <span data-ttu-id="4f13d-246">Estos subelementos están diseñados para ayudar a detectar las repeticiones.</span><span class="sxs-lookup"><span data-stu-id="4f13d-246">These sub-elements are intended to help replay detection.</span></span> <span data-ttu-id="4f13d-247">WCF usa las firmas del mensaje en su lugar.</span><span class="sxs-lookup"><span data-stu-id="4f13d-247">WCF uses message signatures instead.</span></span>  
  
 <span data-ttu-id="4f13d-248">Perfil 1.1 de UsernameToken de seguridad de mensajes SOAP WSS OASIS (UsernameToken11) introdujo la característica de derivación de claves a partir de la contraseña.</span><span class="sxs-lookup"><span data-stu-id="4f13d-248">OASIS WSS SOAP Message Security UsernameToken Profile 1.1 (UsernameToken11) introduced key derivation from password feature.</span></span>  
  
 <span data-ttu-id="4f13d-249">La contraseña de UsernameToken B1103 no se debe utilizar para la derivación de claves ni, por consiguiente, para las operaciones criptográficas.</span><span class="sxs-lookup"><span data-stu-id="4f13d-249">B1103 UsernameToken password MUST not be used for key derivation and therefore for cryptographic operations.</span></span>  
  
 <span data-ttu-id="4f13d-250">Razón: las contraseñas generalmente están consideradas demasiado débiles como para ser utilizadas para operaciones criptográficas.</span><span class="sxs-lookup"><span data-stu-id="4f13d-250">Rationale: passwords are generally considered too weak to be used for cryptographic operations.</span></span>  
  
### <a name="12-x509-token"></a><span data-ttu-id="4f13d-251">1.2 Token X509</span><span class="sxs-lookup"><span data-stu-id="4f13d-251">1.2 X509 Token</span></span>  
 <span data-ttu-id="4f13d-252">WCF admite certificados X509v3 como un tipo de credencial y sigue X509TokenProfile1.0 y X509TokenProfile1.1 con las siguientes restricciones:</span><span class="sxs-lookup"><span data-stu-id="4f13d-252">WCF supports X509v3 certificates as a credential type and follows X509TokenProfile1.0 and X509TokenProfile1.1 with the following constraints:</span></span>  
  
 <span data-ttu-id="4f13d-253">R1201 El atributo ValueType en el elemento BinarySecurityToken debe tener el valor #X509v3 cuando contiene un certificado X509v3.</span><span class="sxs-lookup"><span data-stu-id="4f13d-253">R1201 The ValueType attribute on the BinarySecurityToken element must have value #X509v3 when it contains an X509v3 certificate.</span></span>  
  
 <span data-ttu-id="4f13d-254">Los perfiles 1.0 y 1.1 de token de WSS X509 también definen #X509PKIPathv1 y #PKCS7 como tipos de valor.</span><span class="sxs-lookup"><span data-stu-id="4f13d-254">WSS X509 Token Profile 1.0 and 1.1 define also #X509PKIPathv1 and #PKCS7 as value types.</span></span> <span data-ttu-id="4f13d-255">WCF no admite estos tipos.</span><span class="sxs-lookup"><span data-stu-id="4f13d-255">WCF does not support these types.</span></span>  
  
 <span data-ttu-id="4f13d-256">R1202 Si una extensión SubjectKeyIdentifier (SKI) se encuentra en un certificado X509, se debería utilizar wsse:KeyIdentifier para las referencias externas al token, con el atributo ValueType como #X509SubjectKeyIdentifier, y su contenido el valor codificado en base64 de la extensión SKI del certificado.</span><span class="sxs-lookup"><span data-stu-id="4f13d-256">R1202 If a SubjectKeyIdentifier (SKI) extension is present in an X509 certificate, wsse:KeyIdentifier should be used for external references to the token, with the ValueType attribute as #X509SubjectKeyIdentifier and its content the base64-encoded value of certificate's SKI extension.</span></span>  
  
 <span data-ttu-id="4f13d-257">Las referencias SKI se implementan ampliamente y demuestran ser un tipo de referencia externa muy interoperable.</span><span class="sxs-lookup"><span data-stu-id="4f13d-257">SKI references are widely implemented and proven to be a highly interoperable external reference type.</span></span>  
  
 <span data-ttu-id="4f13d-258">R1203 Una referencia externa al token de seguridad X509 NO DEBERÍA utilizar ds:X509IssuerSerial.</span><span class="sxs-lookup"><span data-stu-id="4f13d-258">R1203 An external Reference to X509 Security Token SHOULD NOT use ds:X509IssuerSerial.</span></span>  
  
 <span data-ttu-id="4f13d-259">R1204 Si se está utilizando X509TokenProfile1.1, una referencia externa al token de seguridad X509 DEBERÍA utilizar la huella digital introducida por WS-Security 1.1.</span><span class="sxs-lookup"><span data-stu-id="4f13d-259">R1204 If X509TokenProfile1.1 is in use, an external reference to X509 Security Token SHOULD use the thumbprint introduced by WS-Security 1.1.</span></span>  
  
 <span data-ttu-id="4f13d-260">WCF admite X509IssuerSerial.</span><span class="sxs-lookup"><span data-stu-id="4f13d-260">WCF supports X509IssuerSerial.</span></span> <span data-ttu-id="4f13d-261">Sin embargo, hay problemas de interoperabilidad con X509IssuerSerial: WCF usa una cadena para comparar dos valores de X509IssuerSerial.</span><span class="sxs-lookup"><span data-stu-id="4f13d-261">However There are interoperability issues with X509IssuerSerial: WCF uses a string to compare two values of X509IssuerSerial.</span></span> <span data-ttu-id="4f13d-262">Por lo tanto, si uno reordena componentes del nombre del sujeto y envía a un servicio WCF, una referencia a un certificado, puede no encontrarlo.</span><span class="sxs-lookup"><span data-stu-id="4f13d-262">Therefore if one reorders components of the Subject Name and sends to an WCF service a reference to a certificate, it may not be found.</span></span>  
  
### <a name="13-kerberos-token"></a><span data-ttu-id="4f13d-263">1.3 Token de Kerberos.</span><span class="sxs-lookup"><span data-stu-id="4f13d-263">1.3 Kerberos Token</span></span>  
 <span data-ttu-id="4f13d-264">WCF admite KerberosTokenProfile1.1 para la autenticación de Windows con las siguientes restricciones:</span><span class="sxs-lookup"><span data-stu-id="4f13d-264">WCF supports KerberosTokenProfile1.1 for the purpose of Windows authentication with the following constraints:</span></span>  
  
 <span data-ttu-id="4f13d-265">R1301 Un Token de Kerberos debe llevar el valor de un AP_REQ de Kerberos v4 ajustado a GSS, tal y como se define en GSS_API y en la especificación de Kerberos, y debe tener el atributo ValueType con el valor #GSS_Kerberosv5_AP_REQ.</span><span class="sxs-lookup"><span data-stu-id="4f13d-265">R1301 A Kerberos Token must carry the value of a GSS wrapped Kerberos v4 AP_REQ as defined in GSS_API and the Kerberos specification, and must have the ValueType attribute with the value #GSS_Kerberosv5_AP_REQ.</span></span>  
  
 <span data-ttu-id="4f13d-266">WCF usa GSS ajustado AP-REQ de Kerberos, no un AP-REQ desnudo</span><span class="sxs-lookup"><span data-stu-id="4f13d-266">WCF uses GSS wrapped Kerberos AP-REQ, not a bare AP-REQ.</span></span> <span data-ttu-id="4f13d-267">Éste es un procedimiento de seguridad recomendado.</span><span class="sxs-lookup"><span data-stu-id="4f13d-267">This is a security best practice.</span></span>  
  
### <a name="14-saml-v11-token"></a><span data-ttu-id="4f13d-268">1.4 Token SAML v1.1</span><span class="sxs-lookup"><span data-stu-id="4f13d-268">1.4 SAML v1.1 Token</span></span>  
 <span data-ttu-id="4f13d-269">WCF admite perfiles de Token de WSS SAML 1.0 y 1.1 para tokens SAML v1.1.</span><span class="sxs-lookup"><span data-stu-id="4f13d-269">WCF supports WSS SAML Token profiles 1.0 and 1.1 for SAML v1.1 tokens.</span></span> <span data-ttu-id="4f13d-270">Es posible implementar otras versiones de formatos de token SAML.</span><span class="sxs-lookup"><span data-stu-id="4f13d-270">It is possible to implement other versions of SAML token formats.</span></span>  
  
### <a name="15-security-context-token"></a><span data-ttu-id="4f13d-271">1.5 Token de contexto de seguridad</span><span class="sxs-lookup"><span data-stu-id="4f13d-271">1.5 Security Context Token</span></span>  
 <span data-ttu-id="4f13d-272">WCF es compatible con el contexto de seguridad Token (SCT) introducido en WS-SecureCoversation.</span><span class="sxs-lookup"><span data-stu-id="4f13d-272">WCF supports the Security Context Token (SCT) introduced in WS-SecureCoversation.</span></span> <span data-ttu-id="4f13d-273">SCT se utiliza para representar un contexto de seguridad establecido en SecureConversation así como los protocolos de negociación binarios TLS y SSPI, descritos a continuación.</span><span class="sxs-lookup"><span data-stu-id="4f13d-273">SCT is used to represent a security context established in SecureConversation as well as the binary negotiation protocols TLS and SSPI, described below.</span></span>  
  
## <a name="2-common-message-security-parameters"></a><span data-ttu-id="4f13d-274">2. Parámetros de seguridad de mensajes comunes</span><span class="sxs-lookup"><span data-stu-id="4f13d-274">2. Common Message Security Parameters</span></span>  
  
### <a name="21-timestamp"></a><span data-ttu-id="4f13d-275">2.1 Marca de tiempo</span><span class="sxs-lookup"><span data-stu-id="4f13d-275">2.1 TimeStamp</span></span>  
 <span data-ttu-id="4f13d-276">La presencia de la marca de tiempo se controla mediante la propiedad <xref:System.ServiceModel.Channels.SecurityBindingElement.IncludeTimestamp%2A> de la clase <xref:System.ServiceModel.Channels.SecurityBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="4f13d-276">Timestamp presence is controlled using the <xref:System.ServiceModel.Channels.SecurityBindingElement.IncludeTimestamp%2A> property of the <xref:System.ServiceModel.Channels.SecurityBindingElement> class.</span></span> <span data-ttu-id="4f13d-277">WCF siempre serializa wsse: timestamp con wsse: crea y wsse: campos que expire.</span><span class="sxs-lookup"><span data-stu-id="4f13d-277">WCF always serializes wsse:TimeStamp with wsse:Created and wsse:Expires fields.</span></span> <span data-ttu-id="4f13d-278">El wsse:TimeStamp siempre se firma cuando se utilizan las firmas.</span><span class="sxs-lookup"><span data-stu-id="4f13d-278">The wsse:TimeStamp is always signed when signing is used.</span></span>  
  
### <a name="22-protection-order"></a><span data-ttu-id="4f13d-279">2.2 Orden de protección</span><span class="sxs-lookup"><span data-stu-id="4f13d-279">2.2 Protection Order</span></span>  
 <span data-ttu-id="4f13d-280">WCF admite el orden de protección de mensaje "Inicio de sesión antes de cifrar" y "Cifrar antes de cerrar sesión" (Security Policy 1.1).</span><span class="sxs-lookup"><span data-stu-id="4f13d-280">WCF supports the message protection order "Sign Before Encrypt" and "Encrypt Before Sign" (Security Policy 1.1).</span></span> <span data-ttu-id="4f13d-281">"Sign Before Encrypt" se recomienda por diferentes motivos, entre los que se incluyen los siguientes: los mensajes protegidos mediante Encrypt Before Sign están expuestos a ataques de sustitución de firmas a menos que se use el mecanismo SignatureConfirmation de WS-Security 1.1, y una firma sobre el contenido cifrado dificulta la auditoría.</span><span class="sxs-lookup"><span data-stu-id="4f13d-281">"Sign Before Encrypt" is recommended for reasons including: messages protected with Encrypt Before Sign are open to signature substitution attacks unless the WS-Security 1.1 SignatureConfirmation mechanism is used, and a signature over encrypted content makes auditing harder.</span></span>  
  
### <a name="23-signature-protection"></a><span data-ttu-id="4f13d-282">2.3 Protección de firmas</span><span class="sxs-lookup"><span data-stu-id="4f13d-282">2.3 Signature Protection</span></span>  
 <span data-ttu-id="4f13d-283">Cuando se usa Cifrar antes de firmar, se recomienda proteger la firma para evitar los ataques por fuerza bruta para adivinar el contenido cifrado o la clave de la firma (sobre todo cuando un token personalizado se utiliza con material de clave débil).</span><span class="sxs-lookup"><span data-stu-id="4f13d-283">When Encrypt Before Sign is used, it is recommended to protect the signature to prevent brute force attacks for guessing the encrypted content or the signing key (especially when a custom token is used with weak key material).</span></span>  
  
### <a name="24-algorithm-suite"></a><span data-ttu-id="4f13d-284">2.4 Conjunto de algoritmos</span><span class="sxs-lookup"><span data-stu-id="4f13d-284">2.4 Algorithm Suite</span></span>  
 <span data-ttu-id="4f13d-285">WCF es compatible con todos los conjuntos de algoritmos enumerados en la directiva de seguridad 1.1.</span><span class="sxs-lookup"><span data-stu-id="4f13d-285">WCF supports all algorithm suites listed in Security Policy 1.1.</span></span>  
  
### <a name="25-key-derivation"></a><span data-ttu-id="4f13d-286">2.5 Derivación de clave</span><span class="sxs-lookup"><span data-stu-id="4f13d-286">2.5 Key Derivation</span></span>  
 <span data-ttu-id="4f13d-287">WCF usa "Derivación de clave para las claves simétricas" tal como se describe en WS-SecureConversation.</span><span class="sxs-lookup"><span data-stu-id="4f13d-287">WCF uses "Key Derivation for symmetric keys" as described in WS-SecureConversation.</span></span>  
  
### <a name="26-signature-confirmation"></a><span data-ttu-id="4f13d-288">2.6 Confirmación de firma</span><span class="sxs-lookup"><span data-stu-id="4f13d-288">2.6 Signature Confirmation</span></span>  
 <span data-ttu-id="4f13d-289">La confirmación de firma puede ser como protección frente a ataques de intermediarios para proteger el conjunto de firmas.</span><span class="sxs-lookup"><span data-stu-id="4f13d-289">Signature confirmation can be as protection from middle man attacks to protect the set of signatures.</span></span>  
  
### <a name="27-security-header-layout"></a><span data-ttu-id="4f13d-290">2.7 Diseño del encabezado de seguridad</span><span class="sxs-lookup"><span data-stu-id="4f13d-290">2.7 Security Header Layout</span></span>  
 <span data-ttu-id="4f13d-291">Cada modo de autenticación describe un cierto diseño para el encabezado de seguridad.</span><span class="sxs-lookup"><span data-stu-id="4f13d-291">Each authentication mode describes a certain layout for the security header.</span></span> <span data-ttu-id="4f13d-292">Los elementos dentro del encabezado de seguridad se semiordenan.</span><span class="sxs-lookup"><span data-stu-id="4f13d-292">Elements within the security header are semi-ordered.</span></span> <span data-ttu-id="4f13d-293">Para definir el orden de elementos secundarios del encabezado de seguridad, la directiva WS-Security define los siguientes modos de diseño del encabezado de seguridad:</span><span class="sxs-lookup"><span data-stu-id="4f13d-293">To define the order of security header child elements, WS-Security Policy defines the following security header layout modes:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4f13d-294">Strict</span><span class="sxs-lookup"><span data-stu-id="4f13d-294">Strict</span></span>|<span data-ttu-id="4f13d-295">Los elementos se agregan al encabezado de seguridad siguiendo las reglas de diseño descritas en la sección 7.7.1 de la Directiva de seguridad, según un principio general de "declarar antes de usar".</span><span class="sxs-lookup"><span data-stu-id="4f13d-295">Items are added to the security header following the numbered layout rules described in Security Policy section 7.7.1 according to a general principle of "declare before use".</span></span>|  
|<span data-ttu-id="4f13d-296">Lax</span><span class="sxs-lookup"><span data-stu-id="4f13d-296">Lax</span></span>|<span data-ttu-id="4f13d-297">Los elementos se agregan al encabezado de seguridad en cualquier orden conforme a WSS: Seguridad del mensaje SOAP.</span><span class="sxs-lookup"><span data-stu-id="4f13d-297">Items are added to the security header in any order that conforms to WSS: SOAP Message Security.</span></span>|  
|<span data-ttu-id="4f13d-298">LaxTimestampFirst</span><span class="sxs-lookup"><span data-stu-id="4f13d-298">LaxTimestampFirst</span></span>|<span data-ttu-id="4f13d-299">Igual que Lax, solo que el primer elemento en el encabezado de seguridad debe ser wsse:Timestamp</span><span class="sxs-lookup"><span data-stu-id="4f13d-299">Same as Lax except that the first item in the security header must be a wsse:Timestamp</span></span>|  
|<span data-ttu-id="4f13d-300">LaxTimestampLast</span><span class="sxs-lookup"><span data-stu-id="4f13d-300">LaxTimestampLast</span></span>|<span data-ttu-id="4f13d-301">Igual que lax, solo que el último elemento en el encabezado de seguridad debe ser wsse:Timestamp</span><span class="sxs-lookup"><span data-stu-id="4f13d-301">Same as lax except that the last item in the security header must be a wsse:Timestamp</span></span>|  
  
 <span data-ttu-id="4f13d-302">WCF admite los cuatro modos de diseño del encabezado de seguridad.</span><span class="sxs-lookup"><span data-stu-id="4f13d-302">WCF supports all four modes for security header layout.</span></span> <span data-ttu-id="4f13d-303">La estructura de encabezado de Seguridad y los ejemplos de mensajes para los modos de autenticación siguen el modo "Strict" (estricto).</span><span class="sxs-lookup"><span data-stu-id="4f13d-303">Security header structure and message examples for authentication modes below follow the "Strict" mode.</span></span>  
  
## <a name="2-common-message-security-parameters"></a><span data-ttu-id="4f13d-304">2. Parámetros de seguridad de mensajes comunes</span><span class="sxs-lookup"><span data-stu-id="4f13d-304">2. Common Message Security Parameters</span></span>  
 <span data-ttu-id="4f13d-305">En esta sección se proporcionan ejemplos de directivas para cada modo de autenticación junto con ejemplos que muestran la estructura de encabezado de seguridad en mensajes intercambiados por cliente y servicio.</span><span class="sxs-lookup"><span data-stu-id="4f13d-305">This section provides example policies for each authentication mode along with examples showing security header structure in messages exchanged by client and service.</span></span>  
  
### <a name="61-transport-protection"></a><span data-ttu-id="4f13d-306">6.1 Protección de transporte</span><span class="sxs-lookup"><span data-stu-id="4f13d-306">6.1 Transport Protection</span></span>  
 <span data-ttu-id="4f13d-307">WCF proporciona cinco modos de autenticación que utilizan el transporte seguro para proteger los mensajes; UserNameOverTransport, CertificateOverTransport, KerberosOverTransport, IssuedTokenOverTransport y SspiNegotiatedOverTransport.</span><span class="sxs-lookup"><span data-stu-id="4f13d-307">WCF provides five authentication modes that use secure transport to protect messages; UserNameOverTransport, CertificateOverTransport, KerberosOverTransport, IssuedTokenOverTransport and SspiNegotiatedOverTransport.</span></span>  
  
 <span data-ttu-id="4f13d-308">Estos modos de autenticación se construyen utilizando el enlace de transportes descrito en SecurityPolicy.</span><span class="sxs-lookup"><span data-stu-id="4f13d-308">These authentication modes are constructed using the transport binding described in SecurityPolicy.</span></span> <span data-ttu-id="4f13d-309">Para el modo de autenticación de UserNameOverTransport, UsernameToken es un token auxiliar firmado.</span><span class="sxs-lookup"><span data-stu-id="4f13d-309">For the UserNameOverTransport authentication mode the UsernameToken is a signed supporting token.</span></span> <span data-ttu-id="4f13d-310">Para los otros modos de autenticación el token aparece como un token de endoso firmado.</span><span class="sxs-lookup"><span data-stu-id="4f13d-310">For the other authentication modes the token appears as a signed endorsing token.</span></span> <span data-ttu-id="4f13d-311">Los apéndices C.1.2 y C.1.3 de SecurityPolicy describen en detalle el diseño del encabezado de seguridad.</span><span class="sxs-lookup"><span data-stu-id="4f13d-311">Appendix C.1.2 and C.1.3 of SecurityPolicy describe the security header layout in detail.</span></span> <span data-ttu-id="4f13d-312">Los siguientes encabezados de seguridad del ejemplo muestran el diseño estricto para un modo de autenticación determinado.</span><span class="sxs-lookup"><span data-stu-id="4f13d-312">The following example security headers show the Strict layout for a given authentication mode.</span></span>  
  
 <span data-ttu-id="4f13d-313">El valor de propiedad “Derived Keys” para los tokens en todos los casos es "falsa."</span><span class="sxs-lookup"><span data-stu-id="4f13d-313">The value of the "Derived Keys" property for the tokens in all cases is "false".</span></span>  
  
 <span data-ttu-id="4f13d-314">Los valores de las diversas propiedades del enlace de transporte son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="4f13d-314">The values of the various properties of the transport binding are as follows:</span></span>  
  
 <span data-ttu-id="4f13d-315">Marca de tiempo: true</span><span class="sxs-lookup"><span data-stu-id="4f13d-315">Timestamp: true</span></span>  
  
 <span data-ttu-id="4f13d-316">Diseño del encabezado de seguridad: Strict</span><span class="sxs-lookup"><span data-stu-id="4f13d-316">Security Header Layout: Strict</span></span>  
  
 <span data-ttu-id="4f13d-317">Conjunto de algoritmos: Basic256</span><span class="sxs-lookup"><span data-stu-id="4f13d-317">Algorithm Suite: Basic256</span></span>  
  
#### <a name="611-usernameovertransport"></a><span data-ttu-id="4f13d-318">6.1.1 UsernameOverTransport</span><span class="sxs-lookup"><span data-stu-id="4f13d-318">6.1.1 UsernameOverTransport</span></span>  
 <span data-ttu-id="4f13d-319">Con este modo de autenticación, el cliente se autentica con un token de nombre de usuario que aparece en la capa de SOAP como un token auxiliar firmado que siempre se envía desde el iniciador al destinatario.</span><span class="sxs-lookup"><span data-stu-id="4f13d-319">With this authentication mode, the client authenticates with a Username Token which appears at the SOAP layer as a signed supporting token that is always sent from the initiator to the recipient.</span></span> <span data-ttu-id="4f13d-320">La autenticación del servicio se realiza mediante un certificado X.509 en el nivel de transporte.</span><span class="sxs-lookup"><span data-stu-id="4f13d-320">The service is authenticated using an X.509 certificate at the transport layer.</span></span> <span data-ttu-id="4f13d-321">El enlace utilizado es un enlace de transporte.</span><span class="sxs-lookup"><span data-stu-id="4f13d-321">The binding used is a transport binding.</span></span>  
  
 <span data-ttu-id="4f13d-322">Directiva</span><span class="sxs-lookup"><span data-stu-id="4f13d-322">Policy</span></span>  
  
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
  
 <span data-ttu-id="4f13d-323">Diseño del encabezado de seguridad</span><span class="sxs-lookup"><span data-stu-id="4f13d-323">Security Header Layout</span></span>  
  
 <span data-ttu-id="4f13d-324">Request</span><span class="sxs-lookup"><span data-stu-id="4f13d-324">Request</span></span>  
  
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
  
 <span data-ttu-id="4f13d-325">Respuesta</span><span class="sxs-lookup"><span data-stu-id="4f13d-325">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
</wsse:Security>  
```  
  
#### <a name="612-certificateovertransport"></a><span data-ttu-id="4f13d-326">6.1.2 CertificateOverTransport</span><span class="sxs-lookup"><span data-stu-id="4f13d-326">6.1.2 CertificateOverTransport</span></span>  
 <span data-ttu-id="4f13d-327">Con este modo de autenticación el cliente se autentica utilizando un certificado X.509 que aparece en la capa de SOAP como un token auxiliar de aprobación que siempre se envía desde el iniciador al destinatario.</span><span class="sxs-lookup"><span data-stu-id="4f13d-327">With this authentication mode the client authenticates using an X.509 certificate which appears at the SOAP layer as an endorsing supporting token that is always sent from the initiator to the recipient.</span></span> <span data-ttu-id="4f13d-328">La autenticación del servicio se realiza mediante un certificado X.509 en el nivel de transporte.</span><span class="sxs-lookup"><span data-stu-id="4f13d-328">The service is authenticated using an X.509 certificate at the transport layer.</span></span> <span data-ttu-id="4f13d-329">El enlace utilizado es un enlace de transporte.</span><span class="sxs-lookup"><span data-stu-id="4f13d-329">The binding used is a transport binding.</span></span>  
  
 <span data-ttu-id="4f13d-330">Directiva</span><span class="sxs-lookup"><span data-stu-id="4f13d-330">Policy</span></span>  
  
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
  
 <span data-ttu-id="4f13d-331">Diseño del encabezado de seguridad</span><span class="sxs-lookup"><span data-stu-id="4f13d-331">Security Header Layout</span></span>  
  
 <span data-ttu-id="4f13d-332">Request</span><span class="sxs-lookup"><span data-stu-id="4f13d-332">Request</span></span>  
  
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
  
 <span data-ttu-id="4f13d-333">Respuesta</span><span class="sxs-lookup"><span data-stu-id="4f13d-333">Response</span></span>  
  
```xml  
<o:Security>  
  <u:Timestamp u:Id="_0">  
  ...  
  </u:Timestamp>  
</o:Security>  
```  
  
#### <a name="613-issuedtokenovertransport"></a><span data-ttu-id="4f13d-334">6.1.3 IssuedTokenOverTransport</span><span class="sxs-lookup"><span data-stu-id="4f13d-334">6.1.3 IssuedTokenOverTransport</span></span>  
 <span data-ttu-id="4f13d-335">Con este modo de autenticación, el cliente no se autentica al servicio como tal; sino que, en su lugar, presenta un token emitido por un servicio de token de seguridad (STS) y demuestra que conoce una clave compartida.</span><span class="sxs-lookup"><span data-stu-id="4f13d-335">With this authentication mode the client does not authenticate to the service, as such, but rather presents a token issued by a Security Token Service (STS) and proves knowledge of a shared key.</span></span> <span data-ttu-id="4f13d-336">El token emitido aparece en la capa de SOAP como un token auxiliar de aprobación que siempre se envía desde el iniciador al destinatario.</span><span class="sxs-lookup"><span data-stu-id="4f13d-336">The issued token appears at the SOAP layer as an endorsing supporting token that is always sent from the initiator to the recipient.</span></span> <span data-ttu-id="4f13d-337">La autenticación del servicio se realiza mediante un certificado X.509 en el nivel de transporte.</span><span class="sxs-lookup"><span data-stu-id="4f13d-337">The service is authenticated using an X.509 certificate at the transport layer.</span></span> <span data-ttu-id="4f13d-338">El enlace es un enlace de transporte.</span><span class="sxs-lookup"><span data-stu-id="4f13d-338">The binding is a transport binding.</span></span>  
  
 <span data-ttu-id="4f13d-339">Directiva</span><span class="sxs-lookup"><span data-stu-id="4f13d-339">Policy</span></span>  
  
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
  
 <span data-ttu-id="4f13d-340">Diseño del encabezado de seguridad</span><span class="sxs-lookup"><span data-stu-id="4f13d-340">Security Header Layout</span></span>  
  
 <span data-ttu-id="4f13d-341">Request</span><span class="sxs-lookup"><span data-stu-id="4f13d-341">Request</span></span>  
  
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
  
 <span data-ttu-id="4f13d-342">Respuesta</span><span class="sxs-lookup"><span data-stu-id="4f13d-342">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
</wsse:Security>  
```  
  
#### <a name="614-kerberosovertransport"></a><span data-ttu-id="4f13d-343">6.1.4 KerberosOverTransport</span><span class="sxs-lookup"><span data-stu-id="4f13d-343">6.1.4 KerberosOverTransport</span></span>  
 <span data-ttu-id="4f13d-344">Con este modo de autenticación, el cliente se autentica en el servicio utilizando un tique de Kerberos.</span><span class="sxs-lookup"><span data-stu-id="4f13d-344">With this authentication mode the client authenticates to the service using a Kerberos ticket.</span></span> <span data-ttu-id="4f13d-345">El token de Kerberos aparece en la capa de SOAP como un token auxiliar de aprobación.</span><span class="sxs-lookup"><span data-stu-id="4f13d-345">The Kerberos token appears at the SOAP layer as an endorsing supporting token.</span></span> <span data-ttu-id="4f13d-346">La autenticación del servicio se realiza mediante un certificado X.509 en el nivel de transporte.</span><span class="sxs-lookup"><span data-stu-id="4f13d-346">The service is authenticated using an X.509 certificate at the transport layer.</span></span> <span data-ttu-id="4f13d-347">El enlace es un enlace de transporte.</span><span class="sxs-lookup"><span data-stu-id="4f13d-347">The binding is a transport binding.</span></span>  
  
 <span data-ttu-id="4f13d-348">Directiva</span><span class="sxs-lookup"><span data-stu-id="4f13d-348">Policy</span></span>  
  
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
  
 <span data-ttu-id="4f13d-349">Diseño del encabezado de seguridad</span><span class="sxs-lookup"><span data-stu-id="4f13d-349">Security Header Layout</span></span>  
  
 <span data-ttu-id="4f13d-350">Request</span><span class="sxs-lookup"><span data-stu-id="4f13d-350">Request</span></span>  
  
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
  
 <span data-ttu-id="4f13d-351">Respuesta</span><span class="sxs-lookup"><span data-stu-id="4f13d-351">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
</wsse:Security>  
```  
  
#### <a name="615-sspinegotiatedovertransport"></a><span data-ttu-id="4f13d-352">6.1.5 SspiNegotiatedOverTransport</span><span class="sxs-lookup"><span data-stu-id="4f13d-352">6.1.5 SspiNegotiatedOverTransport</span></span>  
 <span data-ttu-id="4f13d-353">Con este modo de negociación, se usa un protocolo de negociación para realizar la autenticación del cliente y del servidor.</span><span class="sxs-lookup"><span data-stu-id="4f13d-353">With this mode a negotiation protocol is used to perform client and server authentication.</span></span> <span data-ttu-id="4f13d-354">Se utiliza Kerberos si es posible; de lo contrario, se utiliza NTLM.</span><span class="sxs-lookup"><span data-stu-id="4f13d-354">Kerberos is used if possible, otherwise NTLM.</span></span> <span data-ttu-id="4f13d-355">El SCT resultante aparece en la capa de SOAP como un token auxiliar de aprobación que siempre se envía desde el iniciador al destinatario.</span><span class="sxs-lookup"><span data-stu-id="4f13d-355">The resulting SCT appears at the SOAP layer as an endorsing supporting token that is always sent from initiator to recipient.</span></span> <span data-ttu-id="4f13d-356">El servicio se autentica además en el nivel de transporte por un certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="4f13d-356">The service is additionally authenticated at the transport layer by an X.509 certificate.</span></span> <span data-ttu-id="4f13d-357">El enlace utilizado es un enlace de transporte.</span><span class="sxs-lookup"><span data-stu-id="4f13d-357">The binding used is a transport binding.</span></span> <span data-ttu-id="4f13d-358">"SPNEGO" (negociación) describe cómo WCF usa el protocolo de negociación binario SSPI con WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="4f13d-358">"SPNEGO" (negotiation) describes how WCF uses SSPI binary negotiation protocol with WS-Trust.</span></span> <span data-ttu-id="4f13d-359">Los ejemplos de encabezados de seguridad de esta sección tienen lugar una vez se ha establecido SCT mediante el protocolo de enlace SPNEGO.</span><span class="sxs-lookup"><span data-stu-id="4f13d-359">Security header examples in this section are after the SCT has been established through the SPNEGO handshake.</span></span>  
  
 <span data-ttu-id="4f13d-360">Directiva</span><span class="sxs-lookup"><span data-stu-id="4f13d-360">Policy</span></span>  
  
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
  
### <a name="security-header-examples"></a><span data-ttu-id="4f13d-361">Ejemplos de encabezados de seguridad</span><span class="sxs-lookup"><span data-stu-id="4f13d-361">Security Header Examples</span></span>  
 <span data-ttu-id="4f13d-362">Una vez se establece el token de contexto de seguridad (SCT) a través del protocolo de enlace de SPNEGO mediante negociación binaria WS-Trust, los mensajes de aplicación tienen encabezados de seguridad con la estructura siguiente.</span><span class="sxs-lookup"><span data-stu-id="4f13d-362">Once the Security Context Token is established through SPNEGO handshake using WS-Trust Binary Negotiation, the application messages have security headers with the following structure.</span></span>  
  
 <span data-ttu-id="4f13d-363">Request</span><span class="sxs-lookup"><span data-stu-id="4f13d-363">Request</span></span>  
  
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
  
 <span data-ttu-id="4f13d-364">Respuesta</span><span class="sxs-lookup"><span data-stu-id="4f13d-364">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
</wsse:Security>  
```  
  
### <a name="62-using-x509-certificates-for-service-authentication"></a><span data-ttu-id="4f13d-365">6.2 Uso de certificados X.509 para la autenticación de servicios</span><span class="sxs-lookup"><span data-stu-id="4f13d-365">6.2 Using X.509 Certificates for Service Authentication</span></span>  
 <span data-ttu-id="4f13d-366">En esta sección se describe los modos de autenticación siguientes: MutualCertificate WSS1.0, Mutual CertificateDuplex, MutualCertificate WSS1.1, AnonymousForCertificate, UserNameForCertificate y IssuedTokenForCertificate.</span><span class="sxs-lookup"><span data-stu-id="4f13d-366">This section describes the following authentication modes: MutualCertificate WSS1.0, Mutual CertificateDuplex, MutualCertificate WSS1.1, AnonymousForCertificate, UserNameForCertificate and IssuedTokenForCertificate.</span></span>  
  
#### <a name="621-mutualcertificate-wss10"></a><span data-ttu-id="4f13d-367">6.2.1 MutualCertificate WSS1.0</span><span class="sxs-lookup"><span data-stu-id="4f13d-367">6.2.1 MutualCertificate WSS1.0</span></span>  
 <span data-ttu-id="4f13d-368">Con este modo de autenticación el cliente autentica mediante un certificado X.509 que aparece en la capa de SOAP como el token del iniciador.</span><span class="sxs-lookup"><span data-stu-id="4f13d-368">With this authentication mode the client authenticates using an X.509 certificate which appears at the SOAP layer as the initiator token.</span></span> <span data-ttu-id="4f13d-369">La autenticación del servicio también se realiza mediante un certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="4f13d-369">The service is also authenticated using an X.509 certificate.</span></span>  
  
 <span data-ttu-id="4f13d-370">El enlace usado es un enlace asimétrico con los valores de propiedad siguientes:</span><span class="sxs-lookup"><span data-stu-id="4f13d-370">The binding used is an asymmetric binding with the following property values:</span></span>  
  
 <span data-ttu-id="4f13d-371">Token del iniciador: el certificado X.509 del cliente, con modo de inclusión establecido en …/IncludeToken/AlwaysToRecipient</span><span class="sxs-lookup"><span data-stu-id="4f13d-371">Initiator Token: the client’s X.509 certificate, with inclusion mode set to …/IncludeToken/AlwaysToRecipient</span></span>  
  
 <span data-ttu-id="4f13d-372">Token del destinatario: Certificado X.509 del servidor, con el modo de inclusión está establecido en .../IncludeToken/Never</span><span class="sxs-lookup"><span data-stu-id="4f13d-372">Recipient Token: Server’s X.509 Certificate, with inclusion mode is set …/IncludeToken/Never</span></span>  
  
 <span data-ttu-id="4f13d-373">Protección de tokens: False</span><span class="sxs-lookup"><span data-stu-id="4f13d-373">Token Protection: False</span></span>  
  
 <span data-ttu-id="4f13d-374">Encabezado completo y firmas de cuerpo: True</span><span class="sxs-lookup"><span data-stu-id="4f13d-374">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="4f13d-375">Orden de protección: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="4f13d-375">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="4f13d-376">Cifrar firma: True</span><span class="sxs-lookup"><span data-stu-id="4f13d-376">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="4f13d-377">Directiva</span><span class="sxs-lookup"><span data-stu-id="4f13d-377">Policy</span></span>  
  
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
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="4f13d-378">Ejemplos de encabezado de seguridad: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="4f13d-378">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="4f13d-379">Request</span><span class="sxs-lookup"><span data-stu-id="4f13d-379">Request</span></span>  
  
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
  
 <span data-ttu-id="4f13d-380">Respuesta</span><span class="sxs-lookup"><span data-stu-id="4f13d-380">Response</span></span>  
  
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
  
 <span data-ttu-id="4f13d-381">Ejemplos de encabezado de seguridad: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="4f13d-381">Security Header Examples: EncryptBeforeSign</span></span>  
  
 <span data-ttu-id="4f13d-382">Request</span><span class="sxs-lookup"><span data-stu-id="4f13d-382">Request</span></span>  
  
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
  
 <span data-ttu-id="4f13d-383">Respuesta</span><span class="sxs-lookup"><span data-stu-id="4f13d-383">Response</span></span>  
  
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
  
#### <a name="622-mutualcertificateduplex"></a><span data-ttu-id="4f13d-384">6.2.2 MutualCertificateDuplex</span><span class="sxs-lookup"><span data-stu-id="4f13d-384">6.2.2 MutualCertificateDuplex</span></span>  
 <span data-ttu-id="4f13d-385">Con este modo de autenticación el cliente autentica mediante un certificado X.509 que aparece en la capa de SOAP como el token del iniciador.</span><span class="sxs-lookup"><span data-stu-id="4f13d-385">With this authentication mode the client authenticates using an X.509 certificate which appears at the SOAP layer as the initiator token.</span></span> <span data-ttu-id="4f13d-386">La autenticación del servicio también se realiza mediante un certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="4f13d-386">The service is also authenticated using an X.509 certificate.</span></span>  
  
 <span data-ttu-id="4f13d-387">El enlace usado es un enlace asimétrico con los valores de propiedad siguientes:</span><span class="sxs-lookup"><span data-stu-id="4f13d-387">The binding used is an asymmetric binding with the following property values:</span></span>  
  
 <span data-ttu-id="4f13d-388">Token del iniciador: X509 del cliente certificado, modo de inclusión establecido en .../IncludeToken/AlwaysToRecipient</span><span class="sxs-lookup"><span data-stu-id="4f13d-388">Initiator Token: Client’s X509 Certificate, inclusion mode is set to …/IncludeToken/AlwaysToRecipient</span></span>  
  
 <span data-ttu-id="4f13d-389">Token del destinatario: X509 del servidor certificado, modo de inclusión establecido en .../IncludeToken/AlwaysToInitiator</span><span class="sxs-lookup"><span data-stu-id="4f13d-389">Recipient Token: Server’s X509 Certificate, inclusion mode is set to …/IncludeToken/AlwaysToInitiator</span></span>  
  
 <span data-ttu-id="4f13d-390">Protección de tokens: False</span><span class="sxs-lookup"><span data-stu-id="4f13d-390">Token Protection: False</span></span>  
  
 <span data-ttu-id="4f13d-391">Encabezado completo y firmas de cuerpo: True</span><span class="sxs-lookup"><span data-stu-id="4f13d-391">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="4f13d-392">Orden de protección: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="4f13d-392">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="4f13d-393">Cifrar firma: True</span><span class="sxs-lookup"><span data-stu-id="4f13d-393">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="4f13d-394">Directiva</span><span class="sxs-lookup"><span data-stu-id="4f13d-394">Policy</span></span>  
  
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
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="4f13d-395">Ejemplos de encabezado de seguridad: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="4f13d-395">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="4f13d-396">Solicitud y respuesta</span><span class="sxs-lookup"><span data-stu-id="4f13d-396">Request and Response</span></span>  
  
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
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="4f13d-397">Ejemplos de encabezado de seguridad: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="4f13d-397">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="4f13d-398">Solicitud y respuesta</span><span class="sxs-lookup"><span data-stu-id="4f13d-398">Request and Response</span></span>  
  
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
  
#### <a name="623-using-symmetricbinding-with-x509-service-authentication"></a><span data-ttu-id="4f13d-399">6.2.3 Uso de SymmetricBinding con autenticación de servicio X.509</span><span class="sxs-lookup"><span data-stu-id="4f13d-399">6.2.3 Using SymmetricBinding with X.509 Service Authentication</span></span>  
 <span data-ttu-id="4f13d-400">"WSS10" proporcionó compatibilidad limitada para escenarios con tokens de X509.</span><span class="sxs-lookup"><span data-stu-id="4f13d-400">"WSS10" provided limited support for scenarios with X509 tokens.</span></span> <span data-ttu-id="4f13d-401">Por ejemplo, no hubo manera de proporcionar protección de cifrado y firma para los mensajes que solo usan tokens de X509 de servicio.</span><span class="sxs-lookup"><span data-stu-id="4f13d-401">For example, there was no way to provide signature and encryption protection for messages using only service X509 token.</span></span> <span data-ttu-id="4f13d-402">"WSS11" introdujo el uso de EncryptedKey como un token simétrico.</span><span class="sxs-lookup"><span data-stu-id="4f13d-402">"WSS11" introduced the usage of EncryptedKey as a symmetric token.</span></span> <span data-ttu-id="4f13d-403">Ahora una clave temporal cifrada para el certificado X.509 de servicio se podría utilizar para la protección de mensajes de solicitud y respuesta.</span><span class="sxs-lookup"><span data-stu-id="4f13d-403">Now a temporary key encrypted for the service's X.509 certificate could be used for both request and response messages protection.</span></span> <span data-ttu-id="4f13d-404">Los modos de autenticación descritos en la sección 6.4 que se encuentra abajo usan este patrón.</span><span class="sxs-lookup"><span data-stu-id="4f13d-404">The authentication modes described in the section 6.4 below use this pattern.</span></span>  
  
 <span data-ttu-id="4f13d-405">WS-SecurityPolicy describe este patrón utilizando SymmetricBinding con token X509 de servicio como el token de protección.</span><span class="sxs-lookup"><span data-stu-id="4f13d-405">WS-SecurityPolicy describes this pattern using SymmetricBinding with Service X509 token as the protection token.</span></span>  
  
 <span data-ttu-id="4f13d-406">Los modos de autenticación AnonymousForCertificate, UsernameForCertificate, MutualCertificate WSS11 e IssuedTokenForCertificate usan una instancia similar de sp:SymmetricBinding con los siguientes valores de propiedad:</span><span class="sxs-lookup"><span data-stu-id="4f13d-406">Authentication modes AnonymousForCertificate, UsernameForCertificate, MutualCertificate WSS11 and IssuedTokenForCertificate all use a similar instance of sp:SymmetricBinding with the following property values:</span></span>  
  
 <span data-ttu-id="4f13d-407">Token de protección: X509 del servidor certificado, modo de inclusión establecido en .../IncludeToken/Never</span><span class="sxs-lookup"><span data-stu-id="4f13d-407">Protection Token: Server’s X509 Certificate, inclusion mode is set to .../IncludeToken/Never</span></span>  
<span data-ttu-id="4f13d-408">Protección de tokens: False</span><span class="sxs-lookup"><span data-stu-id="4f13d-408">Token Protection: False</span></span>  
  
 <span data-ttu-id="4f13d-409">Encabezado completo y firmas de cuerpo: True</span><span class="sxs-lookup"><span data-stu-id="4f13d-409">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="4f13d-410">Orden de protección: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="4f13d-410">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="4f13d-411">Cifrar firma: True</span><span class="sxs-lookup"><span data-stu-id="4f13d-411">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="4f13d-412">Los modos de autenticación anteriores solo difieren en los tokens auxiliares que utilizan.</span><span class="sxs-lookup"><span data-stu-id="4f13d-412">The above authentication modes only differ by the supporting tokens they use.</span></span> <span data-ttu-id="4f13d-413">AnonymousForCertificate no tiene ningún token auxiliar, MutualCertificate WSS 1.1 tiene el certificado X509 de cliente como un token auxiliar de aprobación, UserNameForCertificate tiene un token de nombre de usuario como un token auxiliar firmado e IssuedTokenForCertificate tiene el token emitido como un token auxiliar de aprobación.</span><span class="sxs-lookup"><span data-stu-id="4f13d-413">AnonymousForCertificate does not have any supporting tokens, MutualCertificate WSS 1.1 has the client’s X509 certificate as an endorsing supporting tokens, UserNameForCertificate has a UserName Token as a signed supporting token and IssuedTokenForCertificate has the issued token as an endorsing supporting token.</span></span>  
  
 <span data-ttu-id="4f13d-414">Directiva</span><span class="sxs-lookup"><span data-stu-id="4f13d-414">Policy</span></span>  
  
 <span data-ttu-id="4f13d-415">Enlace simétrico</span><span class="sxs-lookup"><span data-stu-id="4f13d-415">Symmetric Binding</span></span>  
  
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
  
#### <a name="624-anonymousforcertificate"></a><span data-ttu-id="4f13d-416">6.2.4 AnonymousForCertificate</span><span class="sxs-lookup"><span data-stu-id="4f13d-416">6.2.4 AnonymousForCertificate</span></span>  
 <span data-ttu-id="4f13d-417">Con este modo de autenticación, el cliente es anónimo y el servicio se autentica utilizando un certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="4f13d-417">With this authentication mode the client is anonymous and the service is authenticated using an X.509 certificate.</span></span> <span data-ttu-id="4f13d-418">El enlace utilizado es una instancia de enlace simétrico tal y como se describe en 6.4.2.</span><span class="sxs-lookup"><span data-stu-id="4f13d-418">The binding used is an instance of symmetric binding as described in 6.4.2.</span></span>  
  
 <span data-ttu-id="4f13d-419">Directiva</span><span class="sxs-lookup"><span data-stu-id="4f13d-419">Policy</span></span>  
  
 <span data-ttu-id="4f13d-420">Vea "Directiva" en 6.2.3 más arriba para obtener detalles sobre enlaces</span><span class="sxs-lookup"><span data-stu-id="4f13d-420">See "Policy" in 6.2.3 above for binding details</span></span>  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="4f13d-421">Ejemplos de encabezado de seguridad: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="4f13d-421">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="4f13d-422">Request</span><span class="sxs-lookup"><span data-stu-id="4f13d-422">Request</span></span>  
  
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
  
 <span data-ttu-id="4f13d-423">Respuesta</span><span class="sxs-lookup"><span data-stu-id="4f13d-423">Response</span></span>  
  
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
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="4f13d-424">Ejemplos de encabezado de seguridad: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="4f13d-424">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="4f13d-425">Request</span><span class="sxs-lookup"><span data-stu-id="4f13d-425">Request</span></span>  
  
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
  
 <span data-ttu-id="4f13d-426">Respuesta</span><span class="sxs-lookup"><span data-stu-id="4f13d-426">Response</span></span>  
  
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
  
#### <a name="625-usernameforcertificate"></a><span data-ttu-id="4f13d-427">6.2.5 UserNameForCertificate</span><span class="sxs-lookup"><span data-stu-id="4f13d-427">6.2.5 UserNameForCertificate</span></span>  
 <span data-ttu-id="4f13d-428">Con este modo de autenticación el cliente se autentica en el servicio utilizando un token de nombre de usuario que aparece en la capa SOAP como un token auxiliar firmado.</span><span class="sxs-lookup"><span data-stu-id="4f13d-428">With this authentication mode the client authenticates to the service using a Username Token which appears at the SOAP layer as a signed supporting token.</span></span> <span data-ttu-id="4f13d-429">El servicio autentica al cliente utilizando un certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="4f13d-429">The service authenticates to the client using an X.509 certificate.</span></span> <span data-ttu-id="4f13d-430">El enlace utilizado es un enlace simétrico donde el token de protección es una clave generada por el cliente, cifrada con la clave pública del servicio.</span><span class="sxs-lookup"><span data-stu-id="4f13d-430">The binding used is a symmetric binding with the protection token being a key generated by the client, encrypted with the public key of the service.</span></span>  
  
 <span data-ttu-id="4f13d-431">Directiva</span><span class="sxs-lookup"><span data-stu-id="4f13d-431">Policy</span></span>  
  
 <span data-ttu-id="4f13d-432">Vea "Directiva" en 6.2.3 más arriba para obtener detalles sobre enlaces</span><span class="sxs-lookup"><span data-stu-id="4f13d-432">See "Policy" in 6.2.3 above for binding details</span></span>  
  
 <span data-ttu-id="4f13d-433">Token auxiliar firmado</span><span class="sxs-lookup"><span data-stu-id="4f13d-433">Signed Supporting Token</span></span>  
  
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
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="4f13d-434">Ejemplos de encabezado de seguridad: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="4f13d-434">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="4f13d-435">Request</span><span class="sxs-lookup"><span data-stu-id="4f13d-435">Request</span></span>  
  
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
  
 <span data-ttu-id="4f13d-436">Respuesta</span><span class="sxs-lookup"><span data-stu-id="4f13d-436">Response</span></span>  
  
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
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="4f13d-437">Ejemplos de encabezado de seguridad: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="4f13d-437">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="4f13d-438">Request</span><span class="sxs-lookup"><span data-stu-id="4f13d-438">Request</span></span>  
  
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
  
 <span data-ttu-id="4f13d-439">Respuesta</span><span class="sxs-lookup"><span data-stu-id="4f13d-439">Response</span></span>  
  
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
  
#### <a name="626-mutualcertificate-wss-11"></a><span data-ttu-id="4f13d-440">6.2.6 MutualCertificate (WSS 1.1)</span><span class="sxs-lookup"><span data-stu-id="4f13d-440">6.2.6 MutualCertificate (WSS 1.1)</span></span>  
 <span data-ttu-id="4f13d-441">Con este modo de autenticación el cliente se autentica mediante un certificado X.509 que aparece en la capa SOAP como el token auxiliar de aprobación.</span><span class="sxs-lookup"><span data-stu-id="4f13d-441">With this authentication mode the client authenticates using an X.509 certificate which appears at the SOAP layer as an endorsing supporting token.</span></span> <span data-ttu-id="4f13d-442">La autenticación del servicio también se realiza mediante un certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="4f13d-442">The service is also authenticated using an X.509 certificate.</span></span> <span data-ttu-id="4f13d-443">El enlace utilizado es un enlace simétrico donde el token de protección es una clave generada por el cliente, cifrada con la clave pública del servicio.</span><span class="sxs-lookup"><span data-stu-id="4f13d-443">The binding used is a symmetric binding with the protection token being a key generated by the client, encrypted with the public key of the service.</span></span>  
  
 <span data-ttu-id="4f13d-444">Directiva</span><span class="sxs-lookup"><span data-stu-id="4f13d-444">Policy</span></span>  
  
 <span data-ttu-id="4f13d-445">Vea Directiva en 6.2.3 para obtener detalles sobre enlaces</span><span class="sxs-lookup"><span data-stu-id="4f13d-445">See Policy in 6.2.3 for binding details</span></span>  
  
 <span data-ttu-id="4f13d-446">Aprobar token auxiliar</span><span class="sxs-lookup"><span data-stu-id="4f13d-446">Endorsing Supporting Token</span></span>  
  
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
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="4f13d-447">Ejemplos de encabezado de seguridad: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="4f13d-447">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="4f13d-448">Request</span><span class="sxs-lookup"><span data-stu-id="4f13d-448">Request</span></span>  
  
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
  
 <span data-ttu-id="4f13d-449">Respuesta</span><span class="sxs-lookup"><span data-stu-id="4f13d-449">Response</span></span>  
  
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
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="4f13d-450">Ejemplos de encabezado de seguridad: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="4f13d-450">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="4f13d-451">Request</span><span class="sxs-lookup"><span data-stu-id="4f13d-451">Request</span></span>  
  
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
  
 <span data-ttu-id="4f13d-452">Respuesta</span><span class="sxs-lookup"><span data-stu-id="4f13d-452">Response</span></span>  
  
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
  
#### <a name="627-issuedtokenforcertificate"></a><span data-ttu-id="4f13d-453">6.2.7 IssuedTokenForCertificate</span><span class="sxs-lookup"><span data-stu-id="4f13d-453">6.2.7 IssuedTokenForCertificate</span></span>  
 <span data-ttu-id="4f13d-454">Con este modo de autenticación, el cliente no se autentica al servicio como tal; sino que, en su lugar, presenta un token emitido por un STS y demuestra que conoce una clave compartida.</span><span class="sxs-lookup"><span data-stu-id="4f13d-454">With this authentication mode the client does not authenticate to the service, as such, but instead presents a token issued by a STS and proves knowledge of a shared key.</span></span> <span data-ttu-id="4f13d-455">El token emitido aparece en la capa de SOAP como un token auxiliar de aprobación.</span><span class="sxs-lookup"><span data-stu-id="4f13d-455">The issued token appears at the SOAP layer as an endorsing supporting token.</span></span> <span data-ttu-id="4f13d-456">El servicio autentica al cliente utilizando un certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="4f13d-456">The service authenticates to the client using an X.509 certificate.</span></span> <span data-ttu-id="4f13d-457">El enlace utilizado es un enlace simétrico donde el token de protección es una clave generada por el cliente, cifrada con la clave pública del servicio.</span><span class="sxs-lookup"><span data-stu-id="4f13d-457">The binding used is a symmetric binding with the protection token being a key generated by the client, encrypted with the public key of the service.</span></span>  
  
 <span data-ttu-id="4f13d-458">Directiva</span><span class="sxs-lookup"><span data-stu-id="4f13d-458">Policy</span></span>  
  
 <span data-ttu-id="4f13d-459">Vea Directiva en 6.2.3 más arriba para obtener detalles sobre enlaces</span><span class="sxs-lookup"><span data-stu-id="4f13d-459">See Policy in 6.2.3 above for binding details</span></span>  
  
 <span data-ttu-id="4f13d-460">Aprobar token auxiliar</span><span class="sxs-lookup"><span data-stu-id="4f13d-460">Endorsing Supporting Token</span></span>  
  
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
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="4f13d-461">Ejemplos de encabezado de seguridad: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="4f13d-461">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="4f13d-462">Request</span><span class="sxs-lookup"><span data-stu-id="4f13d-462">Request</span></span>  
  
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
  
 <span data-ttu-id="4f13d-463">Respuesta</span><span class="sxs-lookup"><span data-stu-id="4f13d-463">Response</span></span>  
  
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
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="4f13d-464">Ejemplos de encabezado de seguridad: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="4f13d-464">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="4f13d-465">Request</span><span class="sxs-lookup"><span data-stu-id="4f13d-465">Request</span></span>  
  
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
  
 <span data-ttu-id="4f13d-466">Respuesta</span><span class="sxs-lookup"><span data-stu-id="4f13d-466">Response</span></span>  
  
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
  
## <a name="63-kerberos"></a><span data-ttu-id="4f13d-467">6.3 Kerberos</span><span class="sxs-lookup"><span data-stu-id="4f13d-467">6.3 Kerberos</span></span>  
 <span data-ttu-id="4f13d-468">Con este modo de autenticación, el cliente se autentica en el servicio utilizando un tique de Kerberos.</span><span class="sxs-lookup"><span data-stu-id="4f13d-468">With this authentication mode the client authenticates to the service using a Kerberos ticket.</span></span> <span data-ttu-id="4f13d-469">Ese mismo vale también proporciona autenticación del servidor.</span><span class="sxs-lookup"><span data-stu-id="4f13d-469">That same ticket also provides server authentication.</span></span> <span data-ttu-id="4f13d-470">El enlace utilizado es un enlace simétrico con las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="4f13d-470">The binding used is a symmetric binding with the following properties;</span></span>  
  
 <span data-ttu-id="4f13d-471">Token de protección: Vale de Kerberos, modo de inclusión establecido en .../IncludeToken/Once</span><span class="sxs-lookup"><span data-stu-id="4f13d-471">Protection Token: Kerberos Ticket, inclusion mode is set to .../IncludeToken/Once</span></span>  
<span data-ttu-id="4f13d-472">Protección de tokens: False</span><span class="sxs-lookup"><span data-stu-id="4f13d-472">Token Protection: False</span></span>  
  
 <span data-ttu-id="4f13d-473">Encabezado completo y firmas de cuerpo: True</span><span class="sxs-lookup"><span data-stu-id="4f13d-473">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="4f13d-474">Orden de protección: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="4f13d-474">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="4f13d-475">Cifrar firma: True</span><span class="sxs-lookup"><span data-stu-id="4f13d-475">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="4f13d-476">Directiva</span><span class="sxs-lookup"><span data-stu-id="4f13d-476">Policy</span></span>  
  
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
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="4f13d-477">Ejemplos de encabezado de seguridad: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="4f13d-477">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="4f13d-478">Request</span><span class="sxs-lookup"><span data-stu-id="4f13d-478">Request</span></span>  
  
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
  
 <span data-ttu-id="4f13d-479">Respuesta</span><span class="sxs-lookup"><span data-stu-id="4f13d-479">Response</span></span>  
  
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
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="4f13d-480">Ejemplos de encabezado de seguridad: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="4f13d-480">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="4f13d-481">Request</span><span class="sxs-lookup"><span data-stu-id="4f13d-481">Request</span></span>  
  
```xml  
<wsse:Security>  
TBD  
</wsse:Security>  
```  
  
 <span data-ttu-id="4f13d-482">Respuesta</span><span class="sxs-lookup"><span data-stu-id="4f13d-482">Response</span></span>  
  
```xml  
<wsse:Security>  
TBD  
</wsse:Security>  
```  
  
#### <a name="64-issuedtoken"></a><span data-ttu-id="4f13d-483">6.4 IssuedToken</span><span class="sxs-lookup"><span data-stu-id="4f13d-483">6.4 IssuedToken</span></span>  
 <span data-ttu-id="4f13d-484">Con este modo de autenticación, el cliente no se autentica en el servicio como tal; sino que, en su lugar, presenta un token emitido por un STS y demuestra que conoce una clave compartida.</span><span class="sxs-lookup"><span data-stu-id="4f13d-484">With this authentication mode the client does not authenticate to the service, as such, rather the client presents a token issued by an STS and proves knowledge of a shared key.</span></span> <span data-ttu-id="4f13d-485">El servicio no se autentica al cliente como tal, sino que, en su lugar, el STS cifra la clave compartida como parte del token emitido, de manera que solo el servicio puede descifrar la clave.</span><span class="sxs-lookup"><span data-stu-id="4f13d-485">The service is not authenticated to the client, as such, instead the STS encrypts the shared key as part of the issued token such that only the service can decrypt the key.</span></span> <span data-ttu-id="4f13d-486">El enlace utilizado es un enlace simétrico con las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="4f13d-486">The binding used is as symmetric binding with the following properties;</span></span>  
  
 <span data-ttu-id="4f13d-487">Token de protección: Token emitido, modo de inclusión establecido en .../IncludeToken/AlwaysToRecipient</span><span class="sxs-lookup"><span data-stu-id="4f13d-487">Protection Token: Issued Token, inclusion mode is set to .../IncludeToken/AlwaysToRecipient</span></span>  
<span data-ttu-id="4f13d-488">Protección de tokens: False</span><span class="sxs-lookup"><span data-stu-id="4f13d-488">Token Protection: False</span></span>  
  
 <span data-ttu-id="4f13d-489">Encabezado completo y firmas de cuerpo: True</span><span class="sxs-lookup"><span data-stu-id="4f13d-489">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="4f13d-490">Orden de protección: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="4f13d-490">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="4f13d-491">Cifrar firma: True</span><span class="sxs-lookup"><span data-stu-id="4f13d-491">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="4f13d-492">Directiva</span><span class="sxs-lookup"><span data-stu-id="4f13d-492">Policy</span></span>  
  
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
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="4f13d-493">Ejemplos de encabezado de seguridad: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="4f13d-493">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="4f13d-494">Request</span><span class="sxs-lookup"><span data-stu-id="4f13d-494">Request</span></span>  
  
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
  
 <span data-ttu-id="4f13d-495">Respuesta</span><span class="sxs-lookup"><span data-stu-id="4f13d-495">Response</span></span>  
  
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
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="4f13d-496">Ejemplos de encabezado de seguridad: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="4f13d-496">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="4f13d-497">Request</span><span class="sxs-lookup"><span data-stu-id="4f13d-497">Request</span></span>  
  
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
  
 <span data-ttu-id="4f13d-498">Respuesta</span><span class="sxs-lookup"><span data-stu-id="4f13d-498">Response</span></span>  
  
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
  
### <a name="65-using-sslnegotiated-for-service-authentication"></a><span data-ttu-id="4f13d-499">6.5 Uso de SslNegotiated para la autenticación de servicio</span><span class="sxs-lookup"><span data-stu-id="4f13d-499">6.5 Using SslNegotiated for Service Authentication</span></span>  
 <span data-ttu-id="4f13d-500">En esta sección se describe un grupo de modos de autenticación que utilizan un enlace simétrico donde el token de protección es un token de contexto de seguridad por WS-SecureConversation (WS SC), cuyo valor de clave se negocia ejecutando el protocolo TLS sobre mensajes de RST/RSTR de WS-Trust (WS-T).</span><span class="sxs-lookup"><span data-stu-id="4f13d-500">This section describes a group of authentication modes that use a symmetric binding with the protection token being a Security Context Token per WS-SecureConversation (WS-SC) whose key value is negotiated by executing the TLS protocol over WS-Trust (WS-T) RST/RSTR messages.</span></span> <span data-ttu-id="4f13d-501">En TLSNEGO se describen los detalles de la implementación del protocolo de enlace de TLS mediante WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="4f13d-501">Details of the TLS handshake implementation using WS-Trust are described in TLSNEGO.</span></span> <span data-ttu-id="4f13d-502">Aquí en los ejemplos de mensajes supondremos que SCT con un contexto de seguridad asociado ya se establece a través de un protocolo de enlace.</span><span class="sxs-lookup"><span data-stu-id="4f13d-502">Here in the message examples we will assume that SCT with an associated security context is already established through a handshake.</span></span>  
  
 <span data-ttu-id="4f13d-503">El enlace utilizado es un enlace simétrico con las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="4f13d-503">The binding used is a symmetric binding with the following properties;</span></span>  
  
 <span data-ttu-id="4f13d-504">Token de protección: SslContextToken, modo de inclusión establecido en .../IncludeToken/Never</span><span class="sxs-lookup"><span data-stu-id="4f13d-504">Protection Token: SslContextToken, inclusion mode is set to .../IncludeToken/Never</span></span>  
<span data-ttu-id="4f13d-505">Protección de tokens: False</span><span class="sxs-lookup"><span data-stu-id="4f13d-505">Token Protection: False</span></span>  
  
 <span data-ttu-id="4f13d-506">Encabezado completo y firmas de cuerpo: True</span><span class="sxs-lookup"><span data-stu-id="4f13d-506">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="4f13d-507">Orden de protección: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="4f13d-507">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="4f13d-508">Cifrar firma: True</span><span class="sxs-lookup"><span data-stu-id="4f13d-508">Encrypt Signature: True</span></span>  
  
#### <a name="651-policy-for-sslnegotiated-service-authentication"></a><span data-ttu-id="4f13d-509">6.5.1 Directiva para la autenticación de servicio SslNegotiated</span><span class="sxs-lookup"><span data-stu-id="4f13d-509">6.5.1 Policy for SslNegotiated service authentication</span></span>  
 <span data-ttu-id="4f13d-510">La directiva para todos los modos de autenticación de esta sección es similar y solo difieren en los tokens auxiliares firmados o aprobados empleados.</span><span class="sxs-lookup"><span data-stu-id="4f13d-510">Policy for all authentication modes in this section are similar and differ only by specific signed supporting or endorsing tokens used.</span></span>  
  
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
  
#### <a name="652-anonymousforsslnegotiated"></a><span data-ttu-id="4f13d-511">6.5.2 AnonymousForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="4f13d-511">6.5.2 AnonymousForSslNegotiated</span></span>  
 <span data-ttu-id="4f13d-512">Con este modo de autenticación, el cliente es anónimo y el servicio se autentica utilizando un certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="4f13d-512">With this authentication mode the client is anonymous and the service is authenticated using an X.509 certificate.</span></span> <span data-ttu-id="4f13d-513">El enlace utilizado es una instancia de enlace simétrico tal y como se describe en 6.5.1 más arriba.</span><span class="sxs-lookup"><span data-stu-id="4f13d-513">The binding used is an instance of symmetric binding as described in 6.5.1 above.</span></span>  
  
 <span data-ttu-id="4f13d-514">Directiva</span><span class="sxs-lookup"><span data-stu-id="4f13d-514">Policy</span></span>  
  
 <span data-ttu-id="4f13d-515">Vea Directiva en 6.5.1 más arriba para obtener detalles sobre enlaces.</span><span class="sxs-lookup"><span data-stu-id="4f13d-515">See Policy in 6.5.1 above for binding details.</span></span>  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="4f13d-516">Ejemplos de encabezado de seguridad: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="4f13d-516">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="4f13d-517">Request</span><span class="sxs-lookup"><span data-stu-id="4f13d-517">Request</span></span>  
  
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
  
 <span data-ttu-id="4f13d-518">Respuesta</span><span class="sxs-lookup"><span data-stu-id="4f13d-518">Response</span></span>  
  
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
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="4f13d-519">Ejemplos de encabezado de seguridad: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="4f13d-519">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="4f13d-520">Request</span><span class="sxs-lookup"><span data-stu-id="4f13d-520">Request</span></span>  
  
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
  
 <span data-ttu-id="4f13d-521">Respuesta</span><span class="sxs-lookup"><span data-stu-id="4f13d-521">Response</span></span>  
  
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
  
#### <a name="653-usernameforsslnegotiated"></a><span data-ttu-id="4f13d-522">6.5.3 UserNameForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="4f13d-522">6.5.3 UserNameForSslNegotiated</span></span>  
 <span data-ttu-id="4f13d-523">Con este modo de autenticación el cliente se autentica el servicio utilizando un token de nombre de usuario que aparece en la capa SOAP como un token auxiliar firmado.</span><span class="sxs-lookup"><span data-stu-id="4f13d-523">With this authentication mode the client is authenticates using a Username Token which appears at the SOAP layer as a signed supporting token.</span></span> <span data-ttu-id="4f13d-524">La autenticación del servicio se realiza mediante un certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="4f13d-524">The service is authenticated using an X.509 certificate.</span></span> <span data-ttu-id="4f13d-525">El enlace utilizado es una instancia de enlace simétrico tal y como se describe en 6.5.1.</span><span class="sxs-lookup"><span data-stu-id="4f13d-525">The binding used is an instance of symmetric binding as described in 6.5.1.</span></span>  
  
 <span data-ttu-id="4f13d-526">Directiva</span><span class="sxs-lookup"><span data-stu-id="4f13d-526">Policy</span></span>  
  
 <span data-ttu-id="4f13d-527">Vea la sección 6.5.1 anterior para obtener detalles sobre los enlaces</span><span class="sxs-lookup"><span data-stu-id="4f13d-527">See section 6.5.1 above for binding details</span></span>  
  
 <span data-ttu-id="4f13d-528">Token auxiliar firmado</span><span class="sxs-lookup"><span data-stu-id="4f13d-528">Signed Supporting Token</span></span>  
  
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
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="4f13d-529">Ejemplos de encabezado de seguridad: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="4f13d-529">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="4f13d-530">Request</span><span class="sxs-lookup"><span data-stu-id="4f13d-530">Request</span></span>  
  
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
  
 <span data-ttu-id="4f13d-531">Respuesta</span><span class="sxs-lookup"><span data-stu-id="4f13d-531">Response</span></span>  
  
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
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="4f13d-532">Ejemplos de encabezado de seguridad: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="4f13d-532">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="4f13d-533">Request</span><span class="sxs-lookup"><span data-stu-id="4f13d-533">Request</span></span>  
  
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
  
 <span data-ttu-id="4f13d-534">Respuesta</span><span class="sxs-lookup"><span data-stu-id="4f13d-534">Response</span></span>  
  
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
  
#### <a name="654-issuedtokenforsslnegotiated"></a><span data-ttu-id="4f13d-535">6.5.4 IssuedTokenForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="4f13d-535">6.5.4 IssuedTokenForSslNegotiated</span></span>  
 <span data-ttu-id="4f13d-536">Con este modo de autenticación, el cliente no se autentica al servicio como tal; sino que, en su lugar, presenta un token emitido por un STS y demuestra que conoce una clave compartida.</span><span class="sxs-lookup"><span data-stu-id="4f13d-536">With this authentication mode the client does not authenticate to the service, as such, but instead presents a token issued by an STS and proves knowledge of a shared key.</span></span> <span data-ttu-id="4f13d-537">El token emitido aparece en la capa de SOAP como un token auxiliar de aprobación.</span><span class="sxs-lookup"><span data-stu-id="4f13d-537">The issued token appears at the SOAP layer as an endorsing supporting token.</span></span> <span data-ttu-id="4f13d-538">La autenticación del servicio se realiza mediante un certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="4f13d-538">The service is authenticated using an X.509 certificate.</span></span> <span data-ttu-id="4f13d-539">El enlace utilizado es una instancia de enlace simétrico tal y como se describe en 6.5.1 más arriba.</span><span class="sxs-lookup"><span data-stu-id="4f13d-539">The binding used is an instance of symmetric binding as described in 6.5.1 above.</span></span>  
  
 <span data-ttu-id="4f13d-540">Directiva</span><span class="sxs-lookup"><span data-stu-id="4f13d-540">Policy</span></span>  
  
 <span data-ttu-id="4f13d-541">Vea la sección 6.5.1 anterior para obtener detalles sobre los enlaces</span><span class="sxs-lookup"><span data-stu-id="4f13d-541">See section 6.5.1 above for binding details</span></span>  
  
 <span data-ttu-id="4f13d-542">Aprobar token auxiliar</span><span class="sxs-lookup"><span data-stu-id="4f13d-542">Endorsing Supporting Token</span></span>  
  
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
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="4f13d-543">Ejemplos de encabezado de seguridad: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="4f13d-543">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="4f13d-544">Request</span><span class="sxs-lookup"><span data-stu-id="4f13d-544">Request</span></span>  
  
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
  
 <span data-ttu-id="4f13d-545">Respuesta</span><span class="sxs-lookup"><span data-stu-id="4f13d-545">Response</span></span>  
  
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
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="4f13d-546">Ejemplos de encabezado de seguridad: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="4f13d-546">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="4f13d-547">Request</span><span class="sxs-lookup"><span data-stu-id="4f13d-547">Request</span></span>  
  
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
  
 <span data-ttu-id="4f13d-548">Respuesta</span><span class="sxs-lookup"><span data-stu-id="4f13d-548">Response</span></span>  
  
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
  
#### <a name="655-mutualsslnegotiated"></a><span data-ttu-id="4f13d-549">6.5.5 MutualSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="4f13d-549">6.5.5 MutualSslNegotiated</span></span>  
 <span data-ttu-id="4f13d-550">Con este modo de autenticación, el cliente y el servicio autentican utilizando los certificados X.509.</span><span class="sxs-lookup"><span data-stu-id="4f13d-550">With this authentication mode the client and the service authenticate using X.509 certificates.</span></span> <span data-ttu-id="4f13d-551">El enlace utilizado es una instancia de enlace simétrico tal y como se describe en 6.5.1 más arriba.</span><span class="sxs-lookup"><span data-stu-id="4f13d-551">The binding used is an instance of symmetric binding as described in 6.5.1 above.</span></span>  
  
 <span data-ttu-id="4f13d-552">Directiva</span><span class="sxs-lookup"><span data-stu-id="4f13d-552">Policy</span></span>  
  
 <span data-ttu-id="4f13d-553">Vea la sección 6.5.1 anterior para obtener detalles sobre los enlaces</span><span class="sxs-lookup"><span data-stu-id="4f13d-553">See section 6.5.1 above for binding details</span></span>  
  
 <span data-ttu-id="4f13d-554">Aprobar token auxiliar</span><span class="sxs-lookup"><span data-stu-id="4f13d-554">Endorsing Supporting Token</span></span>  
  
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
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="4f13d-555">Ejemplos de encabezado de seguridad: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="4f13d-555">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="4f13d-556">Request</span><span class="sxs-lookup"><span data-stu-id="4f13d-556">Request</span></span>  
  
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
  
 <span data-ttu-id="4f13d-557">Respuesta</span><span class="sxs-lookup"><span data-stu-id="4f13d-557">Response</span></span>  
  
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
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="4f13d-558">Ejemplos de encabezado de seguridad: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="4f13d-558">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="4f13d-559">Request</span><span class="sxs-lookup"><span data-stu-id="4f13d-559">Request</span></span>  
  
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
  
 <span data-ttu-id="4f13d-560">Respuesta</span><span class="sxs-lookup"><span data-stu-id="4f13d-560">Response</span></span>  
  
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
  
### <a name="66-sspinegotiated"></a><span data-ttu-id="4f13d-561">6.6 SspiNegotiated</span><span class="sxs-lookup"><span data-stu-id="4f13d-561">6.6 SspiNegotiated</span></span>  
 <span data-ttu-id="4f13d-562">Con este modo de autenticación, se usa un protocolo de negociación para realizar la autenticación del cliente y del servidor.</span><span class="sxs-lookup"><span data-stu-id="4f13d-562">With this authentication mode a negotiation protocol is used to perform client and server authentication.</span></span> <span data-ttu-id="4f13d-563">Se utiliza Kerberos si es posible; de lo contrario, se utiliza NTLM.</span><span class="sxs-lookup"><span data-stu-id="4f13d-563">Kerberos is used if possible, otherwise NTLM.</span></span> <span data-ttu-id="4f13d-564">El enlace utilizado es un enlace simétrico con las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="4f13d-564">The binding used is a symmetric binding with the following properties;</span></span>  
  
 <span data-ttu-id="4f13d-565">Token de protección: SpnegoContextToken, modo de inclusión establecido en .../IncludeToken/AlwaysToRecipient</span><span class="sxs-lookup"><span data-stu-id="4f13d-565">Protection Token: SpnegoContextToken, inclusion mode is set to .../IncludeToken/AlwaysToRecipient</span></span>  
<span data-ttu-id="4f13d-566">Protección de tokens: False</span><span class="sxs-lookup"><span data-stu-id="4f13d-566">Token Protection: False</span></span>  
  
 <span data-ttu-id="4f13d-567">Encabezado completo y firmas de cuerpo: True</span><span class="sxs-lookup"><span data-stu-id="4f13d-567">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="4f13d-568">Orden de protección: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="4f13d-568">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="4f13d-569">Cifrar firma: True</span><span class="sxs-lookup"><span data-stu-id="4f13d-569">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="4f13d-570">Directiva</span><span class="sxs-lookup"><span data-stu-id="4f13d-570">Policy</span></span>  
  
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
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="4f13d-571">Ejemplos de encabezado de seguridad: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="4f13d-571">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="4f13d-572">Request</span><span class="sxs-lookup"><span data-stu-id="4f13d-572">Request</span></span>  
  
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
  
 <span data-ttu-id="4f13d-573">Respuesta</span><span class="sxs-lookup"><span data-stu-id="4f13d-573">Response</span></span>  
  
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
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="4f13d-574">Ejemplos de encabezado de seguridad: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="4f13d-574">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="4f13d-575">Request</span><span class="sxs-lookup"><span data-stu-id="4f13d-575">Request</span></span>  
  
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
  
 <span data-ttu-id="4f13d-576">Respuesta</span><span class="sxs-lookup"><span data-stu-id="4f13d-576">Response</span></span>  
  
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
  
### <a name="67-secureconversation"></a><span data-ttu-id="4f13d-577">6.7 SecureConversation</span><span class="sxs-lookup"><span data-stu-id="4f13d-577">6.7 SecureConversation</span></span>  
 <span data-ttu-id="4f13d-578">El enlace utilizado es un enlace simétrico donde el token de protección es un SCT por WS-SecureConversation (WS SC).</span><span class="sxs-lookup"><span data-stu-id="4f13d-578">The binding used is a symmetric binding with the protection token being a SCT per WS-SecureConversation (WS-SC).</span></span> <span data-ttu-id="4f13d-579">El SCT se negocia mediante WS-Trust (WS-Trust) o WS-SecureConversation (WS-SC) según un enlace anidado, que es en sí mismo un enlace simétrico que usa un protocolo de negociación.</span><span class="sxs-lookup"><span data-stu-id="4f13d-579">The SCT is negotiated using WS-Trust (WS-Trust) or WS-SecureConversation (WS-SC) according to a nested binding, which is itself a symmetric binding that uses a negotiation protocol.</span></span> <span data-ttu-id="4f13d-580">El protocolo de negociación utilizará Kerberos para realizar la autenticación de cliente y servidor si es posible.</span><span class="sxs-lookup"><span data-stu-id="4f13d-580">The negotiation protocol will use Kerberos to perform client and server authentication if possible.</span></span> <span data-ttu-id="4f13d-581">Si no se puede utilizar Kerberos, se volverá a NTLM.</span><span class="sxs-lookup"><span data-stu-id="4f13d-581">If Kerberos cannot be used, it will fall back to NTLM.</span></span>  
  
 <span data-ttu-id="4f13d-582">Directiva</span><span class="sxs-lookup"><span data-stu-id="4f13d-582">Policy</span></span>  
  
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
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="4f13d-583">Ejemplos de encabezado de seguridad: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="4f13d-583">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="4f13d-584">Request</span><span class="sxs-lookup"><span data-stu-id="4f13d-584">Request</span></span>  
  
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
  
 <span data-ttu-id="4f13d-585">Respuesta</span><span class="sxs-lookup"><span data-stu-id="4f13d-585">Response</span></span>  
  
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
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="4f13d-586">Ejemplos de encabezado de seguridad: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="4f13d-586">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="4f13d-587">Request</span><span class="sxs-lookup"><span data-stu-id="4f13d-587">Request</span></span>  
  
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
  
 <span data-ttu-id="4f13d-588">Respuesta</span><span class="sxs-lookup"><span data-stu-id="4f13d-588">Response</span></span>  
  
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
