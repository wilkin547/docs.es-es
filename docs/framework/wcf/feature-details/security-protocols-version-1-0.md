---
description: 'Más información acerca de: protocolos de seguridad versión 1,0'
title: Protocolos de seguridad versión 1.0
ms.date: 03/30/2017
ms.assetid: ee3402d2-1076-410b-a3cb-fae0372bd7af
ms.openlocfilehash: c807f0b844fb9cb861148afa63d83826a9740c98
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99752735"
---
# <a name="security-protocols-version-10"></a><span data-ttu-id="f1eec-103">Protocolos de seguridad versión 1.0</span><span class="sxs-lookup"><span data-stu-id="f1eec-103">Security Protocols version 1.0</span></span>

<span data-ttu-id="f1eec-104">Los protocolos de seguridad de servicios Web proporcionan mecanismos de seguridad de servicios Web que cubren todos los requisitos de seguridad de mensajería para empresas existentes.</span><span class="sxs-lookup"><span data-stu-id="f1eec-104">The Web Services Security Protocols provide Web services security mechanisms that cover all existing enterprise messaging security requirements.</span></span> <span data-ttu-id="f1eec-105">En esta sección se describen los detalles de la versión 1,0 de Windows Communication Foundation (WCF) (implementada en <xref:System.ServiceModel.Channels.SecurityBindingElement> ) para los siguientes protocolos de seguridad de servicios Web.</span><span class="sxs-lookup"><span data-stu-id="f1eec-105">This section describes the Windows Communication Foundation (WCF) version 1.0 details (implemented in the <xref:System.ServiceModel.Channels.SecurityBindingElement>) for the following Web services security protocols.</span></span>  
  
|<span data-ttu-id="f1eec-106">Especificación/documento</span><span class="sxs-lookup"><span data-stu-id="f1eec-106">Specification/Document</span></span>|<span data-ttu-id="f1eec-107">Vínculo</span><span class="sxs-lookup"><span data-stu-id="f1eec-107">Link</span></span>|  
|-|-|  
|<span data-ttu-id="f1eec-108">WSS: Message Security 1,0 de SOAP</span><span class="sxs-lookup"><span data-stu-id="f1eec-108">WSS: SOAP Message Security 1.0</span></span>|<https://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-soap-message-security-1.0.pdf>|
|<span data-ttu-id="f1eec-109">WSS: Token Profile 1.0 de Username</span><span class="sxs-lookup"><span data-stu-id="f1eec-109">WSS: Username Token Profile 1.0</span></span>|<https://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-username-token-profile-1.0.pdf>|
|<span data-ttu-id="f1eec-110">WSS: Token Profile 1,0 de X509</span><span class="sxs-lookup"><span data-stu-id="f1eec-110">WSS: X509 Token Profile 1.0</span></span>|<https://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-x509-token-profile-1.0.pdf>|
|<span data-ttu-id="f1eec-111">WSS: Token Profile 1.1 de SAML 1,0</span><span class="sxs-lookup"><span data-stu-id="f1eec-111">WSS: SAML 1.1 Token Profile 1.0</span></span>|<https://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.0.pdf>|
|<span data-ttu-id="f1eec-112">WSS: Message Security 1.1 de SOAP</span><span class="sxs-lookup"><span data-stu-id="f1eec-112">WSS: SOAP Message Security 1.1</span></span>|<https://www.oasis-open.org/committees/download.php/16790/wss-v1.1-spec-os-SOAPMessageSecurity.pdf>|
|<span data-ttu-id="f1eec-113">WSS: Token Profile 1.1 de Username</span><span class="sxs-lookup"><span data-stu-id="f1eec-113">WSS Username Token Profile 1.1</span></span>|<https://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-username-token-profile-1.0.pdf>|
|<span data-ttu-id="f1eec-114">WSS: Token Profile 1,1 de X.509</span><span class="sxs-lookup"><span data-stu-id="f1eec-114">WSS: X.509 Token Profile 1.1</span></span>|<https://www.oasis-open.org/committees/download.php/16785/wss-v1.1-spec-os-x509TokenProfile.pdf>|
|<span data-ttu-id="f1eec-115">WSS: Token Profile 1.1 de Kerberos</span><span class="sxs-lookup"><span data-stu-id="f1eec-115">WSS: Kerberos Token Profile 1.1</span></span>|<https://www.oasis-open.org/committees/download.php/16788/wss-v1.1-spec-os-KerberosTokenProfile.pdf>|
|<span data-ttu-id="f1eec-116">WSS: Token Profile 1.1 de SAML 1.1</span><span class="sxs-lookup"><span data-stu-id="f1eec-116">WSS: SAML 1.1 Token Profile 1.1</span></span>|<https://www.oasis-open.org/committees/download.php/16768/wss-v1.1-spec-os-SAMLTokenProfile.pdf>|
|<span data-ttu-id="f1eec-117">WS-Secure Conversation</span><span class="sxs-lookup"><span data-stu-id="f1eec-117">WS-Secure Conversation</span></span>|<http://specs.xmlsoap.org/ws/2005/02/sc/WS-SecureConversation.pdf>|
|<span data-ttu-id="f1eec-118">WS-Trust</span><span class="sxs-lookup"><span data-stu-id="f1eec-118">WS-Trust</span></span>|<http://specs.xmlsoap.org/ws/2005/02/trust/ws-trust.pdf>|
|<span data-ttu-id="f1eec-119">Nota de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="f1eec-119">Application Note:</span></span><br /><br /> <span data-ttu-id="f1eec-120">Uso de WS-Trust para protocolo de enlace TLS</span><span class="sxs-lookup"><span data-stu-id="f1eec-120">Using WS-Trust for TLS Handshake</span></span>|<span data-ttu-id="f1eec-121">Para su publicación</span><span class="sxs-lookup"><span data-stu-id="f1eec-121">To be published</span></span>|  
|<span data-ttu-id="f1eec-122">Nota de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="f1eec-122">Application Note:</span></span><br /><br /> <span data-ttu-id="f1eec-123">Uso de WS-Trust para SPNEGO</span><span class="sxs-lookup"><span data-stu-id="f1eec-123">Using WS-Trust for SPNEGO</span></span>|<span data-ttu-id="f1eec-124">Para su publicación</span><span class="sxs-lookup"><span data-stu-id="f1eec-124">To be published</span></span>|  
|<span data-ttu-id="f1eec-125">Nota de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="f1eec-125">Application Note:</span></span><br /><br /> <span data-ttu-id="f1eec-126">Referencias e identidad de extremos de direccionamiento de servicios Web</span><span class="sxs-lookup"><span data-stu-id="f1eec-126">Web Services Addressing Endpoint References And Identity</span></span>|<span data-ttu-id="f1eec-127">Para su publicación</span><span class="sxs-lookup"><span data-stu-id="f1eec-127">To be published</span></span>|  
|<span data-ttu-id="f1eec-128">WS-SecurityPolicy 1.1</span><span class="sxs-lookup"><span data-stu-id="f1eec-128">WS-SecurityPolicy 1.1</span></span><br /><br /> <span data-ttu-id="f1eec-129">(2005/07)</span><span class="sxs-lookup"><span data-stu-id="f1eec-129">(2005/07)</span></span>|<http://specs.xmlsoap.org/ws/2005/07/securitypolicy/ws-securitypolicy.pdf><br /><br /> <span data-ttu-id="f1eec-130">tal como se ha modificado por [erratas](https://lists.oasis-open.org/archives/ws-sx/200512/msg00017.html) enviadas al Comité técnico de OASIS WS-SX</span><span class="sxs-lookup"><span data-stu-id="f1eec-130">as amended by [errata](https://lists.oasis-open.org/archives/ws-sx/200512/msg00017.html) submitted to OASIS WS-SX Technical Committee</span></span> |  
  
 <span data-ttu-id="f1eec-131">WCF, versión 1, proporciona 17 modos de autenticación que se pueden usar como base para la configuración de seguridad de servicios Web.</span><span class="sxs-lookup"><span data-stu-id="f1eec-131">WCF, version 1, provides 17 authentication modes that can be used as the basis for Web services security configuration.</span></span> <span data-ttu-id="f1eec-132">Cada modo se optimiza para un conjunto común de requisitos de implementación, como:</span><span class="sxs-lookup"><span data-stu-id="f1eec-132">Each mode is optimized for a common set of deployment requirements, such as:</span></span>  
  
- <span data-ttu-id="f1eec-133">Credenciales utilizadas para autenticar cliente y servicio.</span><span class="sxs-lookup"><span data-stu-id="f1eec-133">Credentials used to authenticate client and service.</span></span>  
  
- <span data-ttu-id="f1eec-134">Mecanismos de protección de seguridad de transporte o mensaje.</span><span class="sxs-lookup"><span data-stu-id="f1eec-134">Message or transport security protection mechanisms.</span></span>  
  
- <span data-ttu-id="f1eec-135">Patrones de intercambio de mensajes.</span><span class="sxs-lookup"><span data-stu-id="f1eec-135">Message exchange patterns.</span></span>  
  
|<span data-ttu-id="f1eec-136">Modo de autenticación</span><span class="sxs-lookup"><span data-stu-id="f1eec-136">Authentication Mode</span></span>|<span data-ttu-id="f1eec-137">Autenticación de clientes</span><span class="sxs-lookup"><span data-stu-id="f1eec-137">Client Authentication</span></span>|<span data-ttu-id="f1eec-138">Autenticación de servidor</span><span class="sxs-lookup"><span data-stu-id="f1eec-138">Server Authentication</span></span>|<span data-ttu-id="f1eec-139">Modo</span><span class="sxs-lookup"><span data-stu-id="f1eec-139">Mode</span></span>|  
|-------------------------|---------------------------|---------------------------|----------|  
|<span data-ttu-id="f1eec-140">UserNameOverTransport</span><span class="sxs-lookup"><span data-stu-id="f1eec-140">UserNameOverTransport</span></span>|<span data-ttu-id="f1eec-141">Nombre de usuario/contraseña</span><span class="sxs-lookup"><span data-stu-id="f1eec-141">User name/password</span></span>|<span data-ttu-id="f1eec-142">X509</span><span class="sxs-lookup"><span data-stu-id="f1eec-142">X509</span></span>|<span data-ttu-id="f1eec-143">Transporte</span><span class="sxs-lookup"><span data-stu-id="f1eec-143">Transport</span></span>|  
|<span data-ttu-id="f1eec-144">CertificateOverTransport</span><span class="sxs-lookup"><span data-stu-id="f1eec-144">CertificateOverTransport</span></span>|<span data-ttu-id="f1eec-145">X509</span><span class="sxs-lookup"><span data-stu-id="f1eec-145">X509</span></span>|<span data-ttu-id="f1eec-146">X509</span><span class="sxs-lookup"><span data-stu-id="f1eec-146">X509</span></span>|<span data-ttu-id="f1eec-147">Transporte</span><span class="sxs-lookup"><span data-stu-id="f1eec-147">Transport</span></span>|  
|<span data-ttu-id="f1eec-148">KerberosOverTransport</span><span class="sxs-lookup"><span data-stu-id="f1eec-148">KerberosOverTransport</span></span>|<span data-ttu-id="f1eec-149">Windows</span><span class="sxs-lookup"><span data-stu-id="f1eec-149">Windows</span></span>|<span data-ttu-id="f1eec-150">X509</span><span class="sxs-lookup"><span data-stu-id="f1eec-150">X509</span></span>|<span data-ttu-id="f1eec-151">Transporte</span><span class="sxs-lookup"><span data-stu-id="f1eec-151">Transport</span></span>|  
|<span data-ttu-id="f1eec-152">IssuedTokenOverTransport</span><span class="sxs-lookup"><span data-stu-id="f1eec-152">IssuedTokenOverTransport</span></span>|<span data-ttu-id="f1eec-153">Federado</span><span class="sxs-lookup"><span data-stu-id="f1eec-153">Federated</span></span>|<span data-ttu-id="f1eec-154">X509</span><span class="sxs-lookup"><span data-stu-id="f1eec-154">X509</span></span>|<span data-ttu-id="f1eec-155">Transporte</span><span class="sxs-lookup"><span data-stu-id="f1eec-155">Transport</span></span>|  
|<span data-ttu-id="f1eec-156">SspiNegotiatedOverTransport</span><span class="sxs-lookup"><span data-stu-id="f1eec-156">SspiNegotiatedOverTransport</span></span>|<span data-ttu-id="f1eec-157">Windows SSPI negociado</span><span class="sxs-lookup"><span data-stu-id="f1eec-157">Windows Sspi Negotiated</span></span>|<span data-ttu-id="f1eec-158">Windows SSPI negociado</span><span class="sxs-lookup"><span data-stu-id="f1eec-158">Windows Sspi Negotiated</span></span>|<span data-ttu-id="f1eec-159">Transporte</span><span class="sxs-lookup"><span data-stu-id="f1eec-159">Transport</span></span>|  
|<span data-ttu-id="f1eec-160">AnonymousForCertificate</span><span class="sxs-lookup"><span data-stu-id="f1eec-160">AnonymousForCertificate</span></span>|<span data-ttu-id="f1eec-161">None</span><span class="sxs-lookup"><span data-stu-id="f1eec-161">None</span></span>|<span data-ttu-id="f1eec-162">X509</span><span class="sxs-lookup"><span data-stu-id="f1eec-162">X509</span></span>|<span data-ttu-id="f1eec-163">Message</span><span class="sxs-lookup"><span data-stu-id="f1eec-163">Message</span></span>|  
|<span data-ttu-id="f1eec-164">UserNameForCertificate</span><span class="sxs-lookup"><span data-stu-id="f1eec-164">UserNameForCertificate</span></span>|<span data-ttu-id="f1eec-165">Nombre de usuario/contraseña</span><span class="sxs-lookup"><span data-stu-id="f1eec-165">User name/password</span></span>|<span data-ttu-id="f1eec-166">X509</span><span class="sxs-lookup"><span data-stu-id="f1eec-166">X509</span></span>|<span data-ttu-id="f1eec-167">Message</span><span class="sxs-lookup"><span data-stu-id="f1eec-167">Message</span></span>|  
|<span data-ttu-id="f1eec-168">MutualCertificate</span><span class="sxs-lookup"><span data-stu-id="f1eec-168">MutualCertificate</span></span>|<span data-ttu-id="f1eec-169">X509</span><span class="sxs-lookup"><span data-stu-id="f1eec-169">X509</span></span>|<span data-ttu-id="f1eec-170">X509</span><span class="sxs-lookup"><span data-stu-id="f1eec-170">X509</span></span>|<span data-ttu-id="f1eec-171">Message</span><span class="sxs-lookup"><span data-stu-id="f1eec-171">Message</span></span>|  
|<span data-ttu-id="f1eec-172">MutualCertificateDuplex</span><span class="sxs-lookup"><span data-stu-id="f1eec-172">MutualCertificateDuplex</span></span>|<span data-ttu-id="f1eec-173">X509</span><span class="sxs-lookup"><span data-stu-id="f1eec-173">X509</span></span>|<span data-ttu-id="f1eec-174">X509</span><span class="sxs-lookup"><span data-stu-id="f1eec-174">X509</span></span>|<span data-ttu-id="f1eec-175">Message</span><span class="sxs-lookup"><span data-stu-id="f1eec-175">Message</span></span>|  
|<span data-ttu-id="f1eec-176">IssuedTokenForCertificate</span><span class="sxs-lookup"><span data-stu-id="f1eec-176">IssuedTokenForCertificate</span></span>|<span data-ttu-id="f1eec-177">Federado</span><span class="sxs-lookup"><span data-stu-id="f1eec-177">Federated</span></span>|<span data-ttu-id="f1eec-178">X509</span><span class="sxs-lookup"><span data-stu-id="f1eec-178">X509</span></span>|<span data-ttu-id="f1eec-179">Message</span><span class="sxs-lookup"><span data-stu-id="f1eec-179">Message</span></span>|  
|<span data-ttu-id="f1eec-180">Kerberos</span><span class="sxs-lookup"><span data-stu-id="f1eec-180">Kerberos</span></span>|<span data-ttu-id="f1eec-181">Windows</span><span class="sxs-lookup"><span data-stu-id="f1eec-181">Windows</span></span>|<span data-ttu-id="f1eec-182">Windows</span><span class="sxs-lookup"><span data-stu-id="f1eec-182">Windows</span></span>|<span data-ttu-id="f1eec-183">Message</span><span class="sxs-lookup"><span data-stu-id="f1eec-183">Message</span></span>|  
|<span data-ttu-id="f1eec-184">IssuedToken</span><span class="sxs-lookup"><span data-stu-id="f1eec-184">IssuedToken</span></span>|<span data-ttu-id="f1eec-185">Federado</span><span class="sxs-lookup"><span data-stu-id="f1eec-185">Federated</span></span>|<span data-ttu-id="f1eec-186">Federado</span><span class="sxs-lookup"><span data-stu-id="f1eec-186">Federated</span></span>|<span data-ttu-id="f1eec-187">Message</span><span class="sxs-lookup"><span data-stu-id="f1eec-187">Message</span></span>|  
|<span data-ttu-id="f1eec-188">SspiNegotiated</span><span class="sxs-lookup"><span data-stu-id="f1eec-188">SspiNegotiated</span></span>|<span data-ttu-id="f1eec-189">Windows SSPI negociado</span><span class="sxs-lookup"><span data-stu-id="f1eec-189">Windows Sspi Negotiated</span></span>|<span data-ttu-id="f1eec-190">Windows SSPI negociado</span><span class="sxs-lookup"><span data-stu-id="f1eec-190">Windows Sspi Negotiated</span></span>|<span data-ttu-id="f1eec-191">Message</span><span class="sxs-lookup"><span data-stu-id="f1eec-191">Message</span></span>|  
|<span data-ttu-id="f1eec-192">AnonymousForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="f1eec-192">AnonymousForSslNegotiated</span></span>|<span data-ttu-id="f1eec-193">None</span><span class="sxs-lookup"><span data-stu-id="f1eec-193">None</span></span>|<span data-ttu-id="f1eec-194">X509, TLS-Nego</span><span class="sxs-lookup"><span data-stu-id="f1eec-194">X509, TLS-Nego</span></span>|<span data-ttu-id="f1eec-195">Message</span><span class="sxs-lookup"><span data-stu-id="f1eec-195">Message</span></span>|  
|<span data-ttu-id="f1eec-196">UserNameForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="f1eec-196">UserNameForSslNegotiated</span></span>|<span data-ttu-id="f1eec-197">Nombre de usuario/contraseña</span><span class="sxs-lookup"><span data-stu-id="f1eec-197">User name/password</span></span>|<span data-ttu-id="f1eec-198">X509, TLS-Nego</span><span class="sxs-lookup"><span data-stu-id="f1eec-198">X509, TLS-Nego</span></span>|<span data-ttu-id="f1eec-199">Message</span><span class="sxs-lookup"><span data-stu-id="f1eec-199">Message</span></span>|  
|<span data-ttu-id="f1eec-200">MutualSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="f1eec-200">MutualSslNegotiated</span></span>|<span data-ttu-id="f1eec-201">X509</span><span class="sxs-lookup"><span data-stu-id="f1eec-201">X509</span></span>|<span data-ttu-id="f1eec-202">X509, TLS-Nego</span><span class="sxs-lookup"><span data-stu-id="f1eec-202">X509, TLS-Nego</span></span>|<span data-ttu-id="f1eec-203">Message</span><span class="sxs-lookup"><span data-stu-id="f1eec-203">Message</span></span>|  
|<span data-ttu-id="f1eec-204">IssuedTokenForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="f1eec-204">IssuedTokenForSslNegotiated</span></span>|<span data-ttu-id="f1eec-205">Federado</span><span class="sxs-lookup"><span data-stu-id="f1eec-205">Federated</span></span>|<span data-ttu-id="f1eec-206">X509, TLS-Nego</span><span class="sxs-lookup"><span data-stu-id="f1eec-206">X509, TLS-Nego</span></span>|<span data-ttu-id="f1eec-207">Message</span><span class="sxs-lookup"><span data-stu-id="f1eec-207">Message</span></span>|  
  
 <span data-ttu-id="f1eec-208">Los extremos que usan tales modos de autenticación pueden expresar sus requisitos de seguridad mediante WS-SecurityPolicy (WS-SP).</span><span class="sxs-lookup"><span data-stu-id="f1eec-208">Endpoints using such authentication modes can express their security requirements using WS-SecurityPolicy (WS-SP).</span></span> <span data-ttu-id="f1eec-209">Este documento describe la estructura de mensajes de infraestructura y encabezado de seguridad para cada modo de autenticación y proporciona ejemplos de directivas y mensajes.</span><span class="sxs-lookup"><span data-stu-id="f1eec-209">This document describes the structure of security header and infrastructure messages for each authentication mode and provides examples of policies and messages.</span></span>  
  
 <span data-ttu-id="f1eec-210">WCF aprovecha WS-SecureConversation para proporcionar compatibilidad con sesiones seguras para proteger los intercambios de varios mensajes entre las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="f1eec-210">WCF leverages WS-SecureConversation to provide secure sessions support to protect multi-message exchanges between applications.</span></span>  <span data-ttu-id="f1eec-211">Vea "Sesiones seguras" más abajo para obtener detalles de implementación.</span><span class="sxs-lookup"><span data-stu-id="f1eec-211">See "Secure Sessions" below for implementation details.</span></span>  
  
 <span data-ttu-id="f1eec-212">Además de los modos de autenticación, WCF proporciona opciones de configuración para controlar mecanismos de protección comunes que se aplican a la mayoría de los modos de autenticación basados en seguridad de mensajes, por ejemplo: orden de firma frente a operaciones de cifrado, conjuntos de algoritmos, derivación de claves y confirmación de firma.</span><span class="sxs-lookup"><span data-stu-id="f1eec-212">In addition to authentication modes, WCF provides settings to control common protection mechanisms that apply to most message security-based authentication modes, for example: order of signature versus encryption operations, algorithm suites, key derivation, and signature confirmation.</span></span>  
  
 <span data-ttu-id="f1eec-213">Los siguientes prefijos y espacios de nombres se utilizan en este documento.</span><span class="sxs-lookup"><span data-stu-id="f1eec-213">The following prefixes and namespaces are used in this document.</span></span>  
  
|<span data-ttu-id="f1eec-214">Prefijo</span><span class="sxs-lookup"><span data-stu-id="f1eec-214">Prefix</span></span>|<span data-ttu-id="f1eec-215">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="f1eec-215">Namespace</span></span>|  
|------------|---------------|  
|<span data-ttu-id="f1eec-216">s</span><span class="sxs-lookup"><span data-stu-id="f1eec-216">s</span></span>|<http://www.w3.org/2003/05/soap-envelope/>|
|<span data-ttu-id="f1eec-217">sp</span><span class="sxs-lookup"><span data-stu-id="f1eec-217">sp</span></span>|<http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/>|
|<span data-ttu-id="f1eec-218">a</span><span class="sxs-lookup"><span data-stu-id="f1eec-218">a</span></span>|<http://www.w3.org/2005/08/addressing>|  
|<span data-ttu-id="f1eec-219">wsse</span><span class="sxs-lookup"><span data-stu-id="f1eec-219">wsse</span></span>|<span data-ttu-id="f1eec-220">TBD – OASIS WSS 1,0 URI</span><span class="sxs-lookup"><span data-stu-id="f1eec-220">TBD – OASIS WSS 1.0 URI</span></span>|  
|<span data-ttu-id="f1eec-221">wsse11</span><span class="sxs-lookup"><span data-stu-id="f1eec-221">wsse11</span></span>|<span data-ttu-id="f1eec-222">TBD – OASIS WSS 1.1 URI</span><span class="sxs-lookup"><span data-stu-id="f1eec-222">TBD – OASIS WSS 1.1 URI</span></span>|  
|<span data-ttu-id="f1eec-223">wsu</span><span class="sxs-lookup"><span data-stu-id="f1eec-223">wsu</span></span>|<span data-ttu-id="f1eec-224">TBD – OASIS WSS 1.0 Utility URI</span><span class="sxs-lookup"><span data-stu-id="f1eec-224">TBD – OASIS WSS 1.0 Utility URI</span></span>|  
|<span data-ttu-id="f1eec-225">ds</span><span class="sxs-lookup"><span data-stu-id="f1eec-225">ds</span></span>|<span data-ttu-id="f1eec-226">TBD – W3C XMLDSig URI</span><span class="sxs-lookup"><span data-stu-id="f1eec-226">TBD – W3C XMLDSig URI</span></span>|  
|<span data-ttu-id="f1eec-227">wst</span><span class="sxs-lookup"><span data-stu-id="f1eec-227">wst</span></span>|<span data-ttu-id="f1eec-228">TBD – WS-Trust 2005/02 URI</span><span class="sxs-lookup"><span data-stu-id="f1eec-228">TBD – WS-Trust 2005/02 URI</span></span>|  
|<span data-ttu-id="f1eec-229">wssc</span><span class="sxs-lookup"><span data-stu-id="f1eec-229">wssc</span></span>|<span data-ttu-id="f1eec-230">TBD – WS-SecureConversation 2005/02 URI</span><span class="sxs-lookup"><span data-stu-id="f1eec-230">TBD – WS-SecureConversation 2005/02 URI</span></span>|  
|<span data-ttu-id="f1eec-231">wsaw</span><span class="sxs-lookup"><span data-stu-id="f1eec-231">wsaw</span></span>|<span data-ttu-id="f1eec-232">TBD - Espacio de nombres de directiva WS-Addressing</span><span class="sxs-lookup"><span data-stu-id="f1eec-232">TBD - WS-Addressing policy namespace</span></span>|  
|<span data-ttu-id="f1eec-233">wsp</span><span class="sxs-lookup"><span data-stu-id="f1eec-233">wsp</span></span>|<http://schemas.xmlsoap.org/ws/2004/09/policy>|  
|<span data-ttu-id="f1eec-234">mssp</span><span class="sxs-lookup"><span data-stu-id="f1eec-234">mssp</span></span>|<http://schemas.xmlsoap.org/ws/2005/07/securitypolicy>|
  
## <a name="1-token-profiles"></a><span data-ttu-id="f1eec-235">1. perfiles de token</span><span class="sxs-lookup"><span data-stu-id="f1eec-235">1. Token Profiles</span></span>  

 <span data-ttu-id="f1eec-236">Las especificaciones Seguridad de Servicios web representan la credencial como tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="f1eec-236">Web Services Security specifications represent credential as security tokens.</span></span> <span data-ttu-id="f1eec-237">WCF admite los siguientes tipos de token:</span><span class="sxs-lookup"><span data-stu-id="f1eec-237">WCF supports the following token types:</span></span>  
  
### <a name="11-usernametoken"></a><span data-ttu-id="f1eec-238">1.1 UsernameToken</span><span class="sxs-lookup"><span data-stu-id="f1eec-238">1.1 UsernameToken</span></span>  

 <span data-ttu-id="f1eec-239">WCF sigue los perfiles UsernameToken10 y UsernameToken11 con las siguientes restricciones:</span><span class="sxs-lookup"><span data-stu-id="f1eec-239">WCF follows UsernameToken10 and UsernameToken11 profiles with the following constraints:</span></span>  
  
 <span data-ttu-id="f1eec-240">El atributo R1101 PasswordType en el elemento UsernameToken\Password no se debe omitir ni debe tener el valor #PasswordText (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="f1eec-240">R1101 PasswordType attribute on UsernameToken\Password element MUST be either omitted or have value #PasswordText (default).</span></span>  
  
 <span data-ttu-id="f1eec-241">Uno puede implementar el #PasswordDigest mediante extensibilidad.</span><span class="sxs-lookup"><span data-stu-id="f1eec-241">One can implement the #PasswordDigest using extensibility.</span></span> <span data-ttu-id="f1eec-242">Se ha observado que #PasswordDigest se confunde a menudo como un mecanismo de protección de contraseña suficientemente seguro.</span><span class="sxs-lookup"><span data-stu-id="f1eec-242">It has been observed that #PasswordDigest was often mistaken to be a secure enough password protection mechanism.</span></span> <span data-ttu-id="f1eec-243">Pero #PasswordDigest no puede actuar como un sustituto del cifrado del UsernameToken.</span><span class="sxs-lookup"><span data-stu-id="f1eec-243">But #PasswordDigest cannot serve as a substitute for encryption of the UsernameToken.</span></span> <span data-ttu-id="f1eec-244">El objetivo principal de #PasswordDigest es la protección frente a ataques mediante repetición.</span><span class="sxs-lookup"><span data-stu-id="f1eec-244">The primary goal of #PasswordDigest is protection against replay attacks.</span></span> <span data-ttu-id="f1eec-245">En los modos de autenticación WCF, las amenazas de ataque de reproducción se mitigan mediante el uso de firmas de mensaje.</span><span class="sxs-lookup"><span data-stu-id="f1eec-245">In WCF authentication modes, replay attack threats are mitigated by using message signatures.</span></span>  
  
 <span data-ttu-id="f1eec-246">B1102 WCF nunca emite los subelementos nonce y creados de UsernameToken.</span><span class="sxs-lookup"><span data-stu-id="f1eec-246">B1102 WCF never emits Nonce and Created sub-elements of the UsernameToken.</span></span>  
  
 <span data-ttu-id="f1eec-247">Estos subelementos están diseñados para ayudar a detectar las repeticiones.</span><span class="sxs-lookup"><span data-stu-id="f1eec-247">These sub-elements are intended to help replay detection.</span></span> <span data-ttu-id="f1eec-248">WCF usa firmas de mensaje en su lugar.</span><span class="sxs-lookup"><span data-stu-id="f1eec-248">WCF uses message signatures instead.</span></span>  
  
 <span data-ttu-id="f1eec-249">Perfil 1.1 de UsernameToken de seguridad de mensajes SOAP WSS OASIS (UsernameToken11) introdujo la característica de derivación de claves a partir de la contraseña.</span><span class="sxs-lookup"><span data-stu-id="f1eec-249">OASIS WSS SOAP Message Security UsernameToken Profile 1.1 (UsernameToken11) introduced key derivation from password feature.</span></span>  
  
 <span data-ttu-id="f1eec-250">La contraseña de UsernameToken B1103 no se debe utilizar para la derivación de claves ni, por consiguiente, para las operaciones criptográficas.</span><span class="sxs-lookup"><span data-stu-id="f1eec-250">B1103 UsernameToken password MUST not be used for key derivation and therefore for cryptographic operations.</span></span>  
  
 <span data-ttu-id="f1eec-251">Razón: las contraseñas generalmente están consideradas demasiado débiles como para ser utilizadas para operaciones criptográficas.</span><span class="sxs-lookup"><span data-stu-id="f1eec-251">Rationale: passwords are generally considered too weak to be used for cryptographic operations.</span></span>  
  
### <a name="12-x509-token"></a><span data-ttu-id="f1eec-252">1.2 Token X509</span><span class="sxs-lookup"><span data-stu-id="f1eec-252">1.2 X509 Token</span></span>  

 <span data-ttu-id="f1eec-253">WCF admite certificados X509v3 como un tipo de credencial y sigue X509TokenProfile 1.0 y X509TokenProfile 1.1 con las siguientes restricciones:</span><span class="sxs-lookup"><span data-stu-id="f1eec-253">WCF supports X509v3 certificates as a credential type and follows X509TokenProfile1.0 and X509TokenProfile1.1 with the following constraints:</span></span>  
  
 <span data-ttu-id="f1eec-254">R1201 El atributo ValueType en el elemento BinarySecurityToken debe tener el valor #X509v3 cuando contiene un certificado X509v3.</span><span class="sxs-lookup"><span data-stu-id="f1eec-254">R1201 The ValueType attribute on the BinarySecurityToken element must have value #X509v3 when it contains an X509v3 certificate.</span></span>  
  
 <span data-ttu-id="f1eec-255">Los perfiles 1.0 y 1.1 de token de WSS X509 también definen #X509PKIPathv1 y #PKCS7 como tipos de valor.</span><span class="sxs-lookup"><span data-stu-id="f1eec-255">WSS X509 Token Profile 1.0 and 1.1 define also #X509PKIPathv1 and #PKCS7 as value types.</span></span> <span data-ttu-id="f1eec-256">WCF no admite estos tipos.</span><span class="sxs-lookup"><span data-stu-id="f1eec-256">WCF does not support these types.</span></span>  
  
 <span data-ttu-id="f1eec-257">R1202 Si una extensión SubjectKeyIdentifier (SKI) se encuentra en un certificado X509, se debería utilizar wsse:KeyIdentifier para las referencias externas al token, con el atributo ValueType como #X509SubjectKeyIdentifier, y su contenido el valor codificado en base64 de la extensión SKI del certificado.</span><span class="sxs-lookup"><span data-stu-id="f1eec-257">R1202 If a SubjectKeyIdentifier (SKI) extension is present in an X509 certificate, wsse:KeyIdentifier should be used for external references to the token, with the ValueType attribute as #X509SubjectKeyIdentifier and its content the base64-encoded value of certificate's SKI extension.</span></span>  
  
 <span data-ttu-id="f1eec-258">Las referencias SKI se implementan ampliamente y demuestran ser un tipo de referencia externa muy interoperable.</span><span class="sxs-lookup"><span data-stu-id="f1eec-258">SKI references are widely implemented and proven to be a highly interoperable external reference type.</span></span>  
  
 <span data-ttu-id="f1eec-259">R1203 Una referencia externa al token de seguridad X509 NO DEBERÍA utilizar ds:X509IssuerSerial.</span><span class="sxs-lookup"><span data-stu-id="f1eec-259">R1203 An external Reference to X509 Security Token SHOULD NOT use ds:X509IssuerSerial.</span></span>  
  
 <span data-ttu-id="f1eec-260">R1204 Si se está utilizando X509TokenProfile1.1, una referencia externa al token de seguridad X509 DEBERÍA utilizar la huella digital introducida por WS-Security 1.1.</span><span class="sxs-lookup"><span data-stu-id="f1eec-260">R1204 If X509TokenProfile1.1 is in use, an external reference to X509 Security Token SHOULD use the thumbprint introduced by WS-Security 1.1.</span></span>  
  
 <span data-ttu-id="f1eec-261">WCF es compatible con X509IssuerSerial.</span><span class="sxs-lookup"><span data-stu-id="f1eec-261">WCF supports X509IssuerSerial.</span></span> <span data-ttu-id="f1eec-262">Sin embargo, hay problemas de interoperabilidad con X509IssuerSerial: WCF usa una cadena para comparar dos valores de X509IssuerSerial.</span><span class="sxs-lookup"><span data-stu-id="f1eec-262">However There are interoperability issues with X509IssuerSerial: WCF uses a string to compare two values of X509IssuerSerial.</span></span> <span data-ttu-id="f1eec-263">Por lo tanto, si una reordena los componentes del nombre de sujeto y envía a un servicio WCF una referencia a un certificado, es posible que no se encuentre.</span><span class="sxs-lookup"><span data-stu-id="f1eec-263">Therefore if one reorders components of the Subject Name and sends to an WCF service a reference to a certificate, it may not be found.</span></span>  
  
### <a name="13-kerberos-token"></a><span data-ttu-id="f1eec-264">1.3 Token de Kerberos.</span><span class="sxs-lookup"><span data-stu-id="f1eec-264">1.3 Kerberos Token</span></span>  

 <span data-ttu-id="f1eec-265">WCF admite KerberosTokenProfile 1.1 con el fin de la autenticación de Windows con las siguientes restricciones:</span><span class="sxs-lookup"><span data-stu-id="f1eec-265">WCF supports KerberosTokenProfile1.1 for the purpose of Windows authentication with the following constraints:</span></span>  
  
 <span data-ttu-id="f1eec-266">R1301 Un Token de Kerberos debe llevar el valor de un AP_REQ de Kerberos v4 ajustado a GSS, tal y como se define en GSS_API y en la especificación de Kerberos, y debe tener el atributo ValueType con el valor #GSS_Kerberosv5_AP_REQ.</span><span class="sxs-lookup"><span data-stu-id="f1eec-266">R1301 A Kerberos Token must carry the value of a GSS wrapped Kerberos v4 AP_REQ as defined in GSS_API and the Kerberos specification, and must have the ValueType attribute with the value #GSS_Kerberosv5_AP_REQ.</span></span>  
  
 <span data-ttu-id="f1eec-267">WCF usa la solicitud de AP-REQ Kerberos ajustada de GSS, no una solicitud de AP-REQ.</span><span class="sxs-lookup"><span data-stu-id="f1eec-267">WCF uses GSS wrapped Kerberos AP-REQ, not a bare AP-REQ.</span></span> <span data-ttu-id="f1eec-268">Éste es un procedimiento de seguridad recomendado.</span><span class="sxs-lookup"><span data-stu-id="f1eec-268">This is a security best practice.</span></span>  
  
### <a name="14-saml-v11-token"></a><span data-ttu-id="f1eec-269">1.4 Token SAML v1.1</span><span class="sxs-lookup"><span data-stu-id="f1eec-269">1.4 SAML v1.1 Token</span></span>  

 <span data-ttu-id="f1eec-270">WCF admite los perfiles de token SAML de WSS 1,0 y 1,1 para los tokens SAML v 1.1.</span><span class="sxs-lookup"><span data-stu-id="f1eec-270">WCF supports WSS SAML Token profiles 1.0 and 1.1 for SAML v1.1 tokens.</span></span> <span data-ttu-id="f1eec-271">Es posible implementar otras versiones de formatos de token SAML.</span><span class="sxs-lookup"><span data-stu-id="f1eec-271">It is possible to implement other versions of SAML token formats.</span></span>  
  
### <a name="15-security-context-token"></a><span data-ttu-id="f1eec-272">1.5 Token de contexto de seguridad</span><span class="sxs-lookup"><span data-stu-id="f1eec-272">1.5 Security Context Token</span></span>  

 <span data-ttu-id="f1eec-273">WCF admite el token de contexto de seguridad (SCT) incluido en WS-SecureConversation.</span><span class="sxs-lookup"><span data-stu-id="f1eec-273">WCF supports the Security Context Token (SCT) introduced in WS-SecureConversation.</span></span> <span data-ttu-id="f1eec-274">SCT se utiliza para representar un contexto de seguridad establecido en SecureConversation así como los protocolos de negociación binarios TLS y SSPI, descritos a continuación.</span><span class="sxs-lookup"><span data-stu-id="f1eec-274">SCT is used to represent a security context established in SecureConversation as well as the binary negotiation protocols TLS and SSPI, described below.</span></span>  
  
## <a name="2-common-message-security-parameters"></a><span data-ttu-id="f1eec-275">2. parámetros de seguridad de mensajes comunes</span><span class="sxs-lookup"><span data-stu-id="f1eec-275">2. Common Message Security Parameters</span></span>  
  
### <a name="21-timestamp"></a><span data-ttu-id="f1eec-276">2.1 Marca de tiempo</span><span class="sxs-lookup"><span data-stu-id="f1eec-276">2.1 TimeStamp</span></span>  

 <span data-ttu-id="f1eec-277">La presencia de la marca de tiempo se controla mediante la propiedad <xref:System.ServiceModel.Channels.SecurityBindingElement.IncludeTimestamp%2A> de la clase <xref:System.ServiceModel.Channels.SecurityBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="f1eec-277">Timestamp presence is controlled using the <xref:System.ServiceModel.Channels.SecurityBindingElement.IncludeTimestamp%2A> property of the <xref:System.ServiceModel.Channels.SecurityBindingElement> class.</span></span> <span data-ttu-id="f1eec-278">WCF siempre serializa wsse: TimeStamp con los campos wsse: Created y wsse: Expires.</span><span class="sxs-lookup"><span data-stu-id="f1eec-278">WCF always serializes wsse:TimeStamp with wsse:Created and wsse:Expires fields.</span></span> <span data-ttu-id="f1eec-279">El wsse:TimeStamp siempre se firma cuando se utilizan las firmas.</span><span class="sxs-lookup"><span data-stu-id="f1eec-279">The wsse:TimeStamp is always signed when signing is used.</span></span>  
  
### <a name="22-protection-order"></a><span data-ttu-id="f1eec-280">2.2 Orden de protección</span><span class="sxs-lookup"><span data-stu-id="f1eec-280">2.2 Protection Order</span></span>  

 <span data-ttu-id="f1eec-281">WCF admite el orden de protección de mensajes "firmar antes de cifrar" y "cifrar antes de firmar" (Directiva de seguridad 1,1).</span><span class="sxs-lookup"><span data-stu-id="f1eec-281">WCF supports the message protection order "Sign Before Encrypt" and "Encrypt Before Sign" (Security Policy 1.1).</span></span> <span data-ttu-id="f1eec-282">"Sign Before Encrypt" se recomienda por diferentes motivos, entre los que se incluyen los siguientes: los mensajes protegidos mediante Encrypt Before Sign están expuestos a ataques de sustitución de firmas a menos que se use el mecanismo SignatureConfirmation de WS-Security 1.1, y una firma sobre el contenido cifrado dificulta la auditoría.</span><span class="sxs-lookup"><span data-stu-id="f1eec-282">"Sign Before Encrypt" is recommended for reasons including: messages protected with Encrypt Before Sign are open to signature substitution attacks unless the WS-Security 1.1 SignatureConfirmation mechanism is used, and a signature over encrypted content makes auditing harder.</span></span>  
  
### <a name="23-signature-protection"></a><span data-ttu-id="f1eec-283">2.3 Protección de firmas</span><span class="sxs-lookup"><span data-stu-id="f1eec-283">2.3 Signature Protection</span></span>  

 <span data-ttu-id="f1eec-284">Cuando se usa Cifrar antes de firmar, se recomienda proteger la firma para evitar los ataques por fuerza bruta para adivinar el contenido cifrado o la clave de la firma (sobre todo cuando un token personalizado se utiliza con material de clave débil).</span><span class="sxs-lookup"><span data-stu-id="f1eec-284">When Encrypt Before Sign is used, it is recommended to protect the signature to prevent brute force attacks for guessing the encrypted content or the signing key (especially when a custom token is used with weak key material).</span></span>  
  
### <a name="24-algorithm-suite"></a><span data-ttu-id="f1eec-285">2.4 Conjunto de algoritmos</span><span class="sxs-lookup"><span data-stu-id="f1eec-285">2.4 Algorithm Suite</span></span>  

 <span data-ttu-id="f1eec-286">WCF es compatible con todos los conjuntos de algoritmos enumerados en la Directiva de seguridad 1,1.</span><span class="sxs-lookup"><span data-stu-id="f1eec-286">WCF supports all algorithm suites listed in Security Policy 1.1.</span></span>  
  
### <a name="25-key-derivation"></a><span data-ttu-id="f1eec-287">2.5 Derivación de clave</span><span class="sxs-lookup"><span data-stu-id="f1eec-287">2.5 Key Derivation</span></span>  

 <span data-ttu-id="f1eec-288">WCF usa "derivación de claves para claves simétricas", como se describe en WS-SecureConversation.</span><span class="sxs-lookup"><span data-stu-id="f1eec-288">WCF uses "Key Derivation for symmetric keys" as described in WS-SecureConversation.</span></span>  
  
### <a name="26-signature-confirmation"></a><span data-ttu-id="f1eec-289">2.6 Confirmación de firma</span><span class="sxs-lookup"><span data-stu-id="f1eec-289">2.6 Signature Confirmation</span></span>  

 <span data-ttu-id="f1eec-290">La confirmación de firma puede ser como protección frente a ataques de intermediarios para proteger el conjunto de firmas.</span><span class="sxs-lookup"><span data-stu-id="f1eec-290">Signature confirmation can be as protection from middle man attacks to protect the set of signatures.</span></span>  
  
### <a name="27-security-header-layout"></a><span data-ttu-id="f1eec-291">2.7 Diseño del encabezado de seguridad</span><span class="sxs-lookup"><span data-stu-id="f1eec-291">2.7 Security Header Layout</span></span>  

 <span data-ttu-id="f1eec-292">Cada modo de autenticación describe un cierto diseño para el encabezado de seguridad.</span><span class="sxs-lookup"><span data-stu-id="f1eec-292">Each authentication mode describes a certain layout for the security header.</span></span> <span data-ttu-id="f1eec-293">Los elementos dentro del encabezado de seguridad se semiordenan.</span><span class="sxs-lookup"><span data-stu-id="f1eec-293">Elements within the security header are semi-ordered.</span></span> <span data-ttu-id="f1eec-294">Para definir el orden de elementos secundarios del encabezado de seguridad, la directiva WS-Security define los siguientes modos de diseño del encabezado de seguridad:</span><span class="sxs-lookup"><span data-stu-id="f1eec-294">To define the order of security header child elements, WS-Security Policy defines the following security header layout modes:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f1eec-295">Strict</span><span class="sxs-lookup"><span data-stu-id="f1eec-295">Strict</span></span>|<span data-ttu-id="f1eec-296">Los elementos se agregan al encabezado de seguridad siguiendo las reglas de diseño descritas en la sección 7.7.1 de la Directiva de seguridad, según un principio general de "declarar antes de usar".</span><span class="sxs-lookup"><span data-stu-id="f1eec-296">Items are added to the security header following the numbered layout rules described in Security Policy section 7.7.1 according to a general principle of "declare before use".</span></span>|  
|<span data-ttu-id="f1eec-297">Lax</span><span class="sxs-lookup"><span data-stu-id="f1eec-297">Lax</span></span>|<span data-ttu-id="f1eec-298">Los elementos se agregan al encabezado de seguridad en cualquier orden que cumpla con la seguridad de mensajes WSS: SOAP.</span><span class="sxs-lookup"><span data-stu-id="f1eec-298">Items are added to the security header in any order that conforms to WSS: SOAP Message Security.</span></span>|  
|<span data-ttu-id="f1eec-299">LaxTimestampFirst</span><span class="sxs-lookup"><span data-stu-id="f1eec-299">LaxTimestampFirst</span></span>|<span data-ttu-id="f1eec-300">Igual que Lax, solo que el primer elemento en el encabezado de seguridad debe ser wsse:Timestamp</span><span class="sxs-lookup"><span data-stu-id="f1eec-300">Same as Lax except that the first item in the security header must be a wsse:Timestamp</span></span>|  
|<span data-ttu-id="f1eec-301">LaxTimestampLast</span><span class="sxs-lookup"><span data-stu-id="f1eec-301">LaxTimestampLast</span></span>|<span data-ttu-id="f1eec-302">Igual que lax, solo que el último elemento en el encabezado de seguridad debe ser wsse:Timestamp</span><span class="sxs-lookup"><span data-stu-id="f1eec-302">Same as lax except that the last item in the security header must be a wsse:Timestamp</span></span>|  
  
 <span data-ttu-id="f1eec-303">WCF admite los cuatro modos de diseño del encabezado de seguridad.</span><span class="sxs-lookup"><span data-stu-id="f1eec-303">WCF supports all four modes for security header layout.</span></span> <span data-ttu-id="f1eec-304">La estructura de encabezado de Seguridad y los ejemplos de mensajes para los modos de autenticación siguen el modo "Strict" (estricto).</span><span class="sxs-lookup"><span data-stu-id="f1eec-304">Security header structure and message examples for authentication modes below follow the "Strict" mode.</span></span>  
  
## <a name="2-common-message-security-parameters"></a><span data-ttu-id="f1eec-305">2. parámetros de seguridad de mensajes comunes</span><span class="sxs-lookup"><span data-stu-id="f1eec-305">2. Common Message Security Parameters</span></span>  

 <span data-ttu-id="f1eec-306">En esta sección se proporcionan ejemplos de directivas para cada modo de autenticación junto con ejemplos que muestran la estructura de encabezado de seguridad en mensajes intercambiados por cliente y servicio.</span><span class="sxs-lookup"><span data-stu-id="f1eec-306">This section provides example policies for each authentication mode along with examples showing security header structure in messages exchanged by client and service.</span></span>  
  
### <a name="61-transport-protection"></a><span data-ttu-id="f1eec-307">6.1 Protección de transporte</span><span class="sxs-lookup"><span data-stu-id="f1eec-307">6.1 Transport Protection</span></span>  

 <span data-ttu-id="f1eec-308">WCF proporciona cinco modos de autenticación que utilizan el transporte seguro para proteger los mensajes; UserNameOverTransport, CertificateOverTransport, KerberosOverTransport, IssuedTokenOverTransport y SspiNegotiatedOverTransport.</span><span class="sxs-lookup"><span data-stu-id="f1eec-308">WCF provides five authentication modes that use secure transport to protect messages; UserNameOverTransport, CertificateOverTransport, KerberosOverTransport, IssuedTokenOverTransport and SspiNegotiatedOverTransport.</span></span>  
  
 <span data-ttu-id="f1eec-309">Estos modos de autenticación se construyen utilizando el enlace de transportes descrito en SecurityPolicy.</span><span class="sxs-lookup"><span data-stu-id="f1eec-309">These authentication modes are constructed using the transport binding described in SecurityPolicy.</span></span> <span data-ttu-id="f1eec-310">Para el modo de autenticación de UserNameOverTransport, UsernameToken es un token auxiliar firmado.</span><span class="sxs-lookup"><span data-stu-id="f1eec-310">For the UserNameOverTransport authentication mode the UsernameToken is a signed supporting token.</span></span> <span data-ttu-id="f1eec-311">Para los otros modos de autenticación el token aparece como un token de endoso firmado.</span><span class="sxs-lookup"><span data-stu-id="f1eec-311">For the other authentication modes the token appears as a signed endorsing token.</span></span> <span data-ttu-id="f1eec-312">Los apéndices C.1.2 y C.1.3 de SecurityPolicy describen en detalle el diseño del encabezado de seguridad.</span><span class="sxs-lookup"><span data-stu-id="f1eec-312">Appendix C.1.2 and C.1.3 of SecurityPolicy describe the security header layout in detail.</span></span> <span data-ttu-id="f1eec-313">Los siguientes encabezados de seguridad del ejemplo muestran el diseño estricto para un modo de autenticación determinado.</span><span class="sxs-lookup"><span data-stu-id="f1eec-313">The following example security headers show the Strict layout for a given authentication mode.</span></span>  
  
 <span data-ttu-id="f1eec-314">El valor de propiedad “Derived Keys” para los tokens en todos los casos es "falsa."</span><span class="sxs-lookup"><span data-stu-id="f1eec-314">The value of the "Derived Keys" property for the tokens in all cases is "false".</span></span>  
  
 <span data-ttu-id="f1eec-315">Los valores de las diversas propiedades del enlace de transporte son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="f1eec-315">The values of the various properties of the transport binding are as follows:</span></span>  
  
 <span data-ttu-id="f1eec-316">Marca de tiempo: true</span><span class="sxs-lookup"><span data-stu-id="f1eec-316">Timestamp: true</span></span>  
  
 <span data-ttu-id="f1eec-317">Diseño de encabezado de seguridad: Strict</span><span class="sxs-lookup"><span data-stu-id="f1eec-317">Security Header Layout: Strict</span></span>  
  
 <span data-ttu-id="f1eec-318">Conjunto de algoritmos: Basic256</span><span class="sxs-lookup"><span data-stu-id="f1eec-318">Algorithm Suite: Basic256</span></span>  
  
#### <a name="611-usernameovertransport"></a><span data-ttu-id="f1eec-319">6.1.1 UsernameOverTransport</span><span class="sxs-lookup"><span data-stu-id="f1eec-319">6.1.1 UsernameOverTransport</span></span>  

 <span data-ttu-id="f1eec-320">Con este modo de autenticación, el cliente se autentica con un token de nombre de usuario que aparece en la capa de SOAP como un token auxiliar firmado que siempre se envía desde el iniciador al destinatario.</span><span class="sxs-lookup"><span data-stu-id="f1eec-320">With this authentication mode, the client authenticates with a Username Token which appears at the SOAP layer as a signed supporting token that is always sent from the initiator to the recipient.</span></span> <span data-ttu-id="f1eec-321">La autenticación del servicio se realiza mediante un certificado X.509 en el nivel de transporte.</span><span class="sxs-lookup"><span data-stu-id="f1eec-321">The service is authenticated using an X.509 certificate at the transport layer.</span></span> <span data-ttu-id="f1eec-322">El enlace utilizado es un enlace de transporte.</span><span class="sxs-lookup"><span data-stu-id="f1eec-322">The binding used is a transport binding.</span></span>  
  
 <span data-ttu-id="f1eec-323">Directiva de</span><span class="sxs-lookup"><span data-stu-id="f1eec-323">Policy</span></span>  
  
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
  
 <span data-ttu-id="f1eec-324">Diseño del encabezado de seguridad</span><span class="sxs-lookup"><span data-stu-id="f1eec-324">Security Header Layout</span></span>  
  
 <span data-ttu-id="f1eec-325">Solicitud</span><span class="sxs-lookup"><span data-stu-id="f1eec-325">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wsse:UsernameToken>  
  ...  
  </wsse:UsernameToken>  
</wsse:Security>  
```  
  
 <span data-ttu-id="f1eec-326">Response</span><span class="sxs-lookup"><span data-stu-id="f1eec-326">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
</wsse:Security>  
```  
  
#### <a name="612-certificateovertransport"></a><span data-ttu-id="f1eec-327">6.1.2 CertificateOverTransport</span><span class="sxs-lookup"><span data-stu-id="f1eec-327">6.1.2 CertificateOverTransport</span></span>  

 <span data-ttu-id="f1eec-328">Con este modo de autenticación el cliente se autentica utilizando un certificado X.509 que aparece en la capa de SOAP como un token auxiliar de aprobación que siempre se envía desde el iniciador al destinatario.</span><span class="sxs-lookup"><span data-stu-id="f1eec-328">With this authentication mode the client authenticates using an X.509 certificate which appears at the SOAP layer as an endorsing supporting token that is always sent from the initiator to the recipient.</span></span> <span data-ttu-id="f1eec-329">La autenticación del servicio se realiza mediante un certificado X.509 en el nivel de transporte.</span><span class="sxs-lookup"><span data-stu-id="f1eec-329">The service is authenticated using an X.509 certificate at the transport layer.</span></span> <span data-ttu-id="f1eec-330">El enlace utilizado es un enlace de transporte.</span><span class="sxs-lookup"><span data-stu-id="f1eec-330">The binding used is a transport binding.</span></span>  
  
 <span data-ttu-id="f1eec-331">Directiva de</span><span class="sxs-lookup"><span data-stu-id="f1eec-331">Policy</span></span>  
  
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
  
 <span data-ttu-id="f1eec-332">Diseño del encabezado de seguridad</span><span class="sxs-lookup"><span data-stu-id="f1eec-332">Security Header Layout</span></span>  
  
 <span data-ttu-id="f1eec-333">Solicitud</span><span class="sxs-lookup"><span data-stu-id="f1eec-333">Request</span></span>  
  
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
  
 <span data-ttu-id="f1eec-334">Response</span><span class="sxs-lookup"><span data-stu-id="f1eec-334">Response</span></span>  
  
```xml  
<o:Security>  
  <u:Timestamp u:Id="_0">  
  ...  
  </u:Timestamp>  
</o:Security>  
```  
  
#### <a name="613-issuedtokenovertransport"></a><span data-ttu-id="f1eec-335">6.1.3 IssuedTokenOverTransport</span><span class="sxs-lookup"><span data-stu-id="f1eec-335">6.1.3 IssuedTokenOverTransport</span></span>  

 <span data-ttu-id="f1eec-336">Con este modo de autenticación, el cliente no se autentica al servicio como tal; sino que, en su lugar, presenta un token emitido por un servicio de token de seguridad (STS) y demuestra que conoce una clave compartida.</span><span class="sxs-lookup"><span data-stu-id="f1eec-336">With this authentication mode the client does not authenticate to the service, as such, but rather presents a token issued by a Security Token Service (STS) and proves knowledge of a shared key.</span></span> <span data-ttu-id="f1eec-337">El token emitido aparece en la capa de SOAP como un token auxiliar de aprobación que siempre se envía desde el iniciador al destinatario.</span><span class="sxs-lookup"><span data-stu-id="f1eec-337">The issued token appears at the SOAP layer as an endorsing supporting token that is always sent from the initiator to the recipient.</span></span> <span data-ttu-id="f1eec-338">La autenticación del servicio se realiza mediante un certificado X.509 en el nivel de transporte.</span><span class="sxs-lookup"><span data-stu-id="f1eec-338">The service is authenticated using an X.509 certificate at the transport layer.</span></span> <span data-ttu-id="f1eec-339">El enlace es un enlace de transporte.</span><span class="sxs-lookup"><span data-stu-id="f1eec-339">The binding is a transport binding.</span></span>  
  
 <span data-ttu-id="f1eec-340">Directiva de</span><span class="sxs-lookup"><span data-stu-id="f1eec-340">Policy</span></span>  
  
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
  
 <span data-ttu-id="f1eec-341">Diseño del encabezado de seguridad</span><span class="sxs-lookup"><span data-stu-id="f1eec-341">Security Header Layout</span></span>  
  
 <span data-ttu-id="f1eec-342">Solicitud</span><span class="sxs-lookup"><span data-stu-id="f1eec-342">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1" >  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <saml:Assertion>  
  ...  
  </saml:Assertion>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
</wsse:Security>  
```  
  
 <span data-ttu-id="f1eec-343">Response</span><span class="sxs-lookup"><span data-stu-id="f1eec-343">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
</wsse:Security>  
```  
  
#### <a name="614-kerberosovertransport"></a><span data-ttu-id="f1eec-344">6.1.4 KerberosOverTransport</span><span class="sxs-lookup"><span data-stu-id="f1eec-344">6.1.4 KerberosOverTransport</span></span>  

 <span data-ttu-id="f1eec-345">Con este modo de autenticación, el cliente se autentica en el servicio utilizando un tique de Kerberos.</span><span class="sxs-lookup"><span data-stu-id="f1eec-345">With this authentication mode the client authenticates to the service using a Kerberos ticket.</span></span> <span data-ttu-id="f1eec-346">El token de Kerberos aparece en la capa de SOAP como un token auxiliar de aprobación.</span><span class="sxs-lookup"><span data-stu-id="f1eec-346">The Kerberos token appears at the SOAP layer as an endorsing supporting token.</span></span> <span data-ttu-id="f1eec-347">La autenticación del servicio se realiza mediante un certificado X.509 en el nivel de transporte.</span><span class="sxs-lookup"><span data-stu-id="f1eec-347">The service is authenticated using an X.509 certificate at the transport layer.</span></span> <span data-ttu-id="f1eec-348">El enlace es un enlace de transporte.</span><span class="sxs-lookup"><span data-stu-id="f1eec-348">The binding is a transport binding.</span></span>  
  
 <span data-ttu-id="f1eec-349">Directiva de</span><span class="sxs-lookup"><span data-stu-id="f1eec-349">Policy</span></span>  
  
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
  
 <span data-ttu-id="f1eec-350">Diseño del encabezado de seguridad</span><span class="sxs-lookup"><span data-stu-id="f1eec-350">Security Header Layout</span></span>  
  
 <span data-ttu-id="f1eec-351">Solicitud</span><span class="sxs-lookup"><span data-stu-id="f1eec-351">Request</span></span>  
  
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
  
 <span data-ttu-id="f1eec-352">Response</span><span class="sxs-lookup"><span data-stu-id="f1eec-352">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
</wsse:Security>  
```  
  
#### <a name="615-sspinegotiatedovertransport"></a><span data-ttu-id="f1eec-353">6.1.5 SspiNegotiatedOverTransport</span><span class="sxs-lookup"><span data-stu-id="f1eec-353">6.1.5 SspiNegotiatedOverTransport</span></span>  

 <span data-ttu-id="f1eec-354">Con este modo de negociación, se usa un protocolo de negociación para realizar la autenticación del cliente y del servidor.</span><span class="sxs-lookup"><span data-stu-id="f1eec-354">With this mode a negotiation protocol is used to perform client and server authentication.</span></span> <span data-ttu-id="f1eec-355">Se utiliza Kerberos si es posible; de lo contrario, se utiliza NTLM.</span><span class="sxs-lookup"><span data-stu-id="f1eec-355">Kerberos is used if possible, otherwise NTLM.</span></span> <span data-ttu-id="f1eec-356">El SCT resultante aparece en la capa de SOAP como un token auxiliar de aprobación que siempre se envía desde el iniciador al destinatario.</span><span class="sxs-lookup"><span data-stu-id="f1eec-356">The resulting SCT appears at the SOAP layer as an endorsing supporting token that is always sent from initiator to recipient.</span></span> <span data-ttu-id="f1eec-357">El servicio se autentica además en el nivel de transporte por un certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="f1eec-357">The service is additionally authenticated at the transport layer by an X.509 certificate.</span></span> <span data-ttu-id="f1eec-358">El enlace utilizado es un enlace de transporte.</span><span class="sxs-lookup"><span data-stu-id="f1eec-358">The binding used is a transport binding.</span></span> <span data-ttu-id="f1eec-359">"SPNEGO" (negociación) describe cómo WCF usa el protocolo de negociación binaria SSPI con WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="f1eec-359">"SPNEGO" (negotiation) describes how WCF uses SSPI binary negotiation protocol with WS-Trust.</span></span> <span data-ttu-id="f1eec-360">Los ejemplos de encabezados de seguridad de esta sección tienen lugar una vez se ha establecido SCT mediante el protocolo de enlace SPNEGO.</span><span class="sxs-lookup"><span data-stu-id="f1eec-360">Security header examples in this section are after the SCT has been established through the SPNEGO handshake.</span></span>  
  
 <span data-ttu-id="f1eec-361">Directiva de</span><span class="sxs-lookup"><span data-stu-id="f1eec-361">Policy</span></span>  
  
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
  
### <a name="security-header-examples"></a><span data-ttu-id="f1eec-362">Ejemplos de encabezados de seguridad</span><span class="sxs-lookup"><span data-stu-id="f1eec-362">Security Header Examples</span></span>  

 <span data-ttu-id="f1eec-363">Una vez se establece el token de contexto de seguridad (SCT) a través del protocolo de enlace de SPNEGO mediante negociación binaria WS-Trust, los mensajes de aplicación tienen encabezados de seguridad con la estructura siguiente.</span><span class="sxs-lookup"><span data-stu-id="f1eec-363">Once the Security Context Token is established through SPNEGO handshake using WS-Trust Binary Negotiation, the application messages have security headers with the following structure.</span></span>  
  
 <span data-ttu-id="f1eec-364">Solicitud</span><span class="sxs-lookup"><span data-stu-id="f1eec-364">Request</span></span>  
  
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
  
 <span data-ttu-id="f1eec-365">Response</span><span class="sxs-lookup"><span data-stu-id="f1eec-365">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
</wsse:Security>  
```  
  
### <a name="62-using-x509-certificates-for-service-authentication"></a><span data-ttu-id="f1eec-366">6.2 Uso de certificados X.509 para la autenticación de servicios</span><span class="sxs-lookup"><span data-stu-id="f1eec-366">6.2 Using X.509 Certificates for Service Authentication</span></span>  

 <span data-ttu-id="f1eec-367">En esta sección se describen los modos de autenticación siguientes: MutualCertificate WSS1.0, Mutual CertificateDuplex, MutualCertificate WSS1.1, AnonymousForCertificate, UserNameForCertificate y IssuedTokenForCertificate.</span><span class="sxs-lookup"><span data-stu-id="f1eec-367">This section describes the following authentication modes: MutualCertificate WSS1.0, Mutual CertificateDuplex, MutualCertificate WSS1.1, AnonymousForCertificate, UserNameForCertificate and IssuedTokenForCertificate.</span></span>  
  
#### <a name="621-mutualcertificate-wss10"></a><span data-ttu-id="f1eec-368">6.2.1 MutualCertificate WSS1.0</span><span class="sxs-lookup"><span data-stu-id="f1eec-368">6.2.1 MutualCertificate WSS1.0</span></span>  

 <span data-ttu-id="f1eec-369">Con este modo de autenticación el cliente autentica mediante un certificado X.509 que aparece en la capa de SOAP como el token del iniciador.</span><span class="sxs-lookup"><span data-stu-id="f1eec-369">With this authentication mode the client authenticates using an X.509 certificate which appears at the SOAP layer as the initiator token.</span></span> <span data-ttu-id="f1eec-370">La autenticación del servicio también se realiza mediante un certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="f1eec-370">The service is also authenticated using an X.509 certificate.</span></span>  
  
 <span data-ttu-id="f1eec-371">El enlace usado es un enlace asimétrico con los valores de propiedad siguientes:</span><span class="sxs-lookup"><span data-stu-id="f1eec-371">The binding used is an asymmetric binding with the following property values:</span></span>  
  
 <span data-ttu-id="f1eec-372">Token del iniciador: el certificado X.509 del cliente, con modo de inclusión establecido en …/IncludeToken/AlwaysToRecipient</span><span class="sxs-lookup"><span data-stu-id="f1eec-372">Initiator Token: the client’s X.509 certificate, with inclusion mode set to …/IncludeToken/AlwaysToRecipient</span></span>  
  
 <span data-ttu-id="f1eec-373">Token del destinatario: el certificado X.509 del servidor, con modo de inclusión establecido en …/IncludeToken/Never</span><span class="sxs-lookup"><span data-stu-id="f1eec-373">Recipient Token: Server’s X.509 Certificate, with inclusion mode is set …/IncludeToken/Never</span></span>  
  
 <span data-ttu-id="f1eec-374">Protección de tokens: False</span><span class="sxs-lookup"><span data-stu-id="f1eec-374">Token Protection: False</span></span>  
  
 <span data-ttu-id="f1eec-375">Encabezado completo y firmas de cuerpo: True</span><span class="sxs-lookup"><span data-stu-id="f1eec-375">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="f1eec-376">Orden de protección: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="f1eec-376">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="f1eec-377">Cifrar firma: True</span><span class="sxs-lookup"><span data-stu-id="f1eec-377">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="f1eec-378">Directiva de</span><span class="sxs-lookup"><span data-stu-id="f1eec-378">Policy</span></span>  
  
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
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="f1eec-379">Ejemplos de encabezado de seguridad: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="f1eec-379">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  

 <span data-ttu-id="f1eec-380">Solicitud</span><span class="sxs-lookup"><span data-stu-id="f1eec-380">Request</span></span>  
  
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
  
 <span data-ttu-id="f1eec-381">Response</span><span class="sxs-lookup"><span data-stu-id="f1eec-381">Response</span></span>  
  
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
  
 <span data-ttu-id="f1eec-382">Ejemplos de encabezado de seguridad: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="f1eec-382">Security Header Examples: EncryptBeforeSign</span></span>  
  
 <span data-ttu-id="f1eec-383">Solicitud</span><span class="sxs-lookup"><span data-stu-id="f1eec-383">Request</span></span>  
  
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
  
 <span data-ttu-id="f1eec-384">Response</span><span class="sxs-lookup"><span data-stu-id="f1eec-384">Response</span></span>  
  
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
  
#### <a name="622-mutualcertificateduplex"></a><span data-ttu-id="f1eec-385">6.2.2 MutualCertificateDuplex</span><span class="sxs-lookup"><span data-stu-id="f1eec-385">6.2.2 MutualCertificateDuplex</span></span>  

 <span data-ttu-id="f1eec-386">Con este modo de autenticación el cliente autentica mediante un certificado X.509 que aparece en la capa de SOAP como el token del iniciador.</span><span class="sxs-lookup"><span data-stu-id="f1eec-386">With this authentication mode the client authenticates using an X.509 certificate which appears at the SOAP layer as the initiator token.</span></span> <span data-ttu-id="f1eec-387">La autenticación del servicio también se realiza mediante un certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="f1eec-387">The service is also authenticated using an X.509 certificate.</span></span>  
  
 <span data-ttu-id="f1eec-388">El enlace usado es un enlace asimétrico con los valores de propiedad siguientes:</span><span class="sxs-lookup"><span data-stu-id="f1eec-388">The binding used is an asymmetric binding with the following property values:</span></span>  
  
 <span data-ttu-id="f1eec-389">Token del iniciador: certificado X509 de cliente, modo de inclusión establecido en …/IncludeToken/AlwaysToRecipient</span><span class="sxs-lookup"><span data-stu-id="f1eec-389">Initiator Token: Client’s X509 Certificate, inclusion mode is set to …/IncludeToken/AlwaysToRecipient</span></span>  
  
 <span data-ttu-id="f1eec-390">Token del destinatario: certificado X509 del servidor, modo de inclusión establecido en …/IncludeToken/AlwaysToInitiator</span><span class="sxs-lookup"><span data-stu-id="f1eec-390">Recipient Token: Server’s X509 Certificate, inclusion mode is set to …/IncludeToken/AlwaysToInitiator</span></span>  
  
 <span data-ttu-id="f1eec-391">Protección de tokens: False</span><span class="sxs-lookup"><span data-stu-id="f1eec-391">Token Protection: False</span></span>  
  
 <span data-ttu-id="f1eec-392">Encabezado completo y firmas de cuerpo: True</span><span class="sxs-lookup"><span data-stu-id="f1eec-392">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="f1eec-393">Orden de protección: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="f1eec-393">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="f1eec-394">Cifrar firma: True</span><span class="sxs-lookup"><span data-stu-id="f1eec-394">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="f1eec-395">Directiva de</span><span class="sxs-lookup"><span data-stu-id="f1eec-395">Policy</span></span>  
  
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
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="f1eec-396">Ejemplos de encabezado de seguridad: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="f1eec-396">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  

 <span data-ttu-id="f1eec-397">Solicitud y respuesta</span><span class="sxs-lookup"><span data-stu-id="f1eec-397">Request and Response</span></span>  
  
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
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="f1eec-398">Ejemplos de encabezado de seguridad: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="f1eec-398">Security Header Examples: EncryptBeforeSign</span></span>  

 <span data-ttu-id="f1eec-399">Solicitud y respuesta</span><span class="sxs-lookup"><span data-stu-id="f1eec-399">Request and Response</span></span>  
  
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
  
#### <a name="623-using-symmetricbinding-with-x509-service-authentication"></a><span data-ttu-id="f1eec-400">6.2.3 Uso de SymmetricBinding con autenticación de servicio X.509</span><span class="sxs-lookup"><span data-stu-id="f1eec-400">6.2.3 Using SymmetricBinding with X.509 Service Authentication</span></span>  

 <span data-ttu-id="f1eec-401">"WSS10" proporcionó compatibilidad limitada para escenarios con tokens de X509.</span><span class="sxs-lookup"><span data-stu-id="f1eec-401">"WSS10" provided limited support for scenarios with X509 tokens.</span></span> <span data-ttu-id="f1eec-402">Por ejemplo, no hubo manera de proporcionar protección de cifrado y firma para los mensajes que solo usan tokens de X509 de servicio.</span><span class="sxs-lookup"><span data-stu-id="f1eec-402">For example, there was no way to provide signature and encryption protection for messages using only service X509 token.</span></span> <span data-ttu-id="f1eec-403">"WSS11" introdujo el uso de EncryptedKey como un token simétrico.</span><span class="sxs-lookup"><span data-stu-id="f1eec-403">"WSS11" introduced the usage of EncryptedKey as a symmetric token.</span></span> <span data-ttu-id="f1eec-404">Ahora una clave temporal cifrada para el certificado X.509 de servicio se podría utilizar para la protección de mensajes de solicitud y respuesta.</span><span class="sxs-lookup"><span data-stu-id="f1eec-404">Now a temporary key encrypted for the service's X.509 certificate could be used for both request and response messages protection.</span></span> <span data-ttu-id="f1eec-405">Los modos de autenticación descritos en la sección 6.4 que se encuentra abajo usan este patrón.</span><span class="sxs-lookup"><span data-stu-id="f1eec-405">The authentication modes described in the section 6.4 below use this pattern.</span></span>  
  
 <span data-ttu-id="f1eec-406">WS-SecurityPolicy describe este patrón utilizando SymmetricBinding con token X509 de servicio como el token de protección.</span><span class="sxs-lookup"><span data-stu-id="f1eec-406">WS-SecurityPolicy describes this pattern using SymmetricBinding with Service X509 token as the protection token.</span></span>  
  
 <span data-ttu-id="f1eec-407">Los modos de autenticación AnonymousForCertificate, UsernameForCertificate, MutualCertificate WSS11 e IssuedTokenForCertificate usan una instancia similar de sp:SymmetricBinding con los siguientes valores de propiedad:</span><span class="sxs-lookup"><span data-stu-id="f1eec-407">Authentication modes AnonymousForCertificate, UsernameForCertificate, MutualCertificate WSS11 and IssuedTokenForCertificate all use a similar instance of sp:SymmetricBinding with the following property values:</span></span>  
  
 <span data-ttu-id="f1eec-408">Token de protección: certificado X.509 de servidor, modo de inclusión establecido en .../IncludeToken/Never</span><span class="sxs-lookup"><span data-stu-id="f1eec-408">Protection Token: Server’s X509 Certificate, inclusion mode is set to .../IncludeToken/Never</span></span>  
<span data-ttu-id="f1eec-409">Protección de tokens: False</span><span class="sxs-lookup"><span data-stu-id="f1eec-409">Token Protection: False</span></span>  
  
 <span data-ttu-id="f1eec-410">Encabezado completo y firmas de cuerpo: True</span><span class="sxs-lookup"><span data-stu-id="f1eec-410">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="f1eec-411">Orden de protección: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="f1eec-411">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="f1eec-412">Cifrar firma: True</span><span class="sxs-lookup"><span data-stu-id="f1eec-412">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="f1eec-413">Los modos de autenticación anteriores solo difieren en los tokens auxiliares que utilizan.</span><span class="sxs-lookup"><span data-stu-id="f1eec-413">The above authentication modes only differ by the supporting tokens they use.</span></span> <span data-ttu-id="f1eec-414">AnonymousForCertificate no tiene ningún token auxiliar, MutualCertificate WSS 1.1 tiene el certificado X509 de cliente como un token auxiliar de aprobación, UserNameForCertificate tiene un token de nombre de usuario como un token auxiliar firmado e IssuedTokenForCertificate tiene el token emitido como un token auxiliar de aprobación.</span><span class="sxs-lookup"><span data-stu-id="f1eec-414">AnonymousForCertificate does not have any supporting tokens, MutualCertificate WSS 1.1 has the client’s X509 certificate as an endorsing supporting tokens, UserNameForCertificate has a UserName Token as a signed supporting token and IssuedTokenForCertificate has the issued token as an endorsing supporting token.</span></span>  
  
 <span data-ttu-id="f1eec-415">Directiva de</span><span class="sxs-lookup"><span data-stu-id="f1eec-415">Policy</span></span>  
  
 <span data-ttu-id="f1eec-416">Enlace simétrico</span><span class="sxs-lookup"><span data-stu-id="f1eec-416">Symmetric Binding</span></span>  
  
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
  
#### <a name="624-anonymousforcertificate"></a><span data-ttu-id="f1eec-417">6.2.4 AnonymousForCertificate</span><span class="sxs-lookup"><span data-stu-id="f1eec-417">6.2.4 AnonymousForCertificate</span></span>  

 <span data-ttu-id="f1eec-418">Con este modo de autenticación, el cliente es anónimo y el servicio se autentica utilizando un certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="f1eec-418">With this authentication mode the client is anonymous and the service is authenticated using an X.509 certificate.</span></span> <span data-ttu-id="f1eec-419">El enlace utilizado es una instancia de enlace simétrico tal y como se describe en 6.4.2.</span><span class="sxs-lookup"><span data-stu-id="f1eec-419">The binding used is an instance of symmetric binding as described in 6.4.2.</span></span>  
  
 <span data-ttu-id="f1eec-420">Directiva de</span><span class="sxs-lookup"><span data-stu-id="f1eec-420">Policy</span></span>  
  
 <span data-ttu-id="f1eec-421">Vea "Directiva" en 6.2.3 más arriba para obtener detalles sobre enlaces</span><span class="sxs-lookup"><span data-stu-id="f1eec-421">See "Policy" in 6.2.3 above for binding details</span></span>  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="f1eec-422">Ejemplos de encabezado de seguridad: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="f1eec-422">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  

 <span data-ttu-id="f1eec-423">Solicitud</span><span class="sxs-lookup"><span data-stu-id="f1eec-423">Request</span></span>  
  
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
  
 <span data-ttu-id="f1eec-424">Response</span><span class="sxs-lookup"><span data-stu-id="f1eec-424">Response</span></span>  
  
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
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="f1eec-425">Ejemplos de encabezado de seguridad: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="f1eec-425">Security Header Examples: EncryptBeforeSign</span></span>  

 <span data-ttu-id="f1eec-426">Solicitud</span><span class="sxs-lookup"><span data-stu-id="f1eec-426">Request</span></span>  
  
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
  
 <span data-ttu-id="f1eec-427">Response</span><span class="sxs-lookup"><span data-stu-id="f1eec-427">Response</span></span>  
  
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
  
#### <a name="625-usernameforcertificate"></a><span data-ttu-id="f1eec-428">6.2.5 UserNameForCertificate</span><span class="sxs-lookup"><span data-stu-id="f1eec-428">6.2.5 UserNameForCertificate</span></span>  

 <span data-ttu-id="f1eec-429">Con este modo de autenticación el cliente se autentica en el servicio utilizando un token de nombre de usuario que aparece en la capa SOAP como un token auxiliar firmado.</span><span class="sxs-lookup"><span data-stu-id="f1eec-429">With this authentication mode the client authenticates to the service using a Username Token which appears at the SOAP layer as a signed supporting token.</span></span> <span data-ttu-id="f1eec-430">El servicio autentica al cliente utilizando un certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="f1eec-430">The service authenticates to the client using an X.509 certificate.</span></span> <span data-ttu-id="f1eec-431">El enlace utilizado es un enlace simétrico donde el token de protección es una clave generada por el cliente, cifrada con la clave pública del servicio.</span><span class="sxs-lookup"><span data-stu-id="f1eec-431">The binding used is a symmetric binding with the protection token being a key generated by the client, encrypted with the public key of the service.</span></span>  
  
 <span data-ttu-id="f1eec-432">Directiva de</span><span class="sxs-lookup"><span data-stu-id="f1eec-432">Policy</span></span>  
  
 <span data-ttu-id="f1eec-433">Vea "Directiva" en 6.2.3 más arriba para obtener detalles sobre enlaces</span><span class="sxs-lookup"><span data-stu-id="f1eec-433">See "Policy" in 6.2.3 above for binding details</span></span>  
  
 <span data-ttu-id="f1eec-434">Token auxiliar firmado</span><span class="sxs-lookup"><span data-stu-id="f1eec-434">Signed Supporting Token</span></span>  
  
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
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="f1eec-435">Ejemplos de encabezado de seguridad: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="f1eec-435">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  

 <span data-ttu-id="f1eec-436">Solicitud</span><span class="sxs-lookup"><span data-stu-id="f1eec-436">Request</span></span>  
  
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
  
 <span data-ttu-id="f1eec-437">Response</span><span class="sxs-lookup"><span data-stu-id="f1eec-437">Response</span></span>  
  
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
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="f1eec-438">Ejemplos de encabezado de seguridad: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="f1eec-438">Security Header Examples: EncryptBeforeSign</span></span>  

 <span data-ttu-id="f1eec-439">Solicitud</span><span class="sxs-lookup"><span data-stu-id="f1eec-439">Request</span></span>  
  
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
  
 <span data-ttu-id="f1eec-440">Response</span><span class="sxs-lookup"><span data-stu-id="f1eec-440">Response</span></span>  
  
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
  
#### <a name="626-mutualcertificate-wss-11"></a><span data-ttu-id="f1eec-441">6.2.6 MutualCertificate (WSS 1.1)</span><span class="sxs-lookup"><span data-stu-id="f1eec-441">6.2.6 MutualCertificate (WSS 1.1)</span></span>  

 <span data-ttu-id="f1eec-442">Con este modo de autenticación el cliente se autentica mediante un certificado X.509 que aparece en la capa SOAP como el token auxiliar de aprobación.</span><span class="sxs-lookup"><span data-stu-id="f1eec-442">With this authentication mode the client authenticates using an X.509 certificate which appears at the SOAP layer as an endorsing supporting token.</span></span> <span data-ttu-id="f1eec-443">La autenticación del servicio también se realiza mediante un certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="f1eec-443">The service is also authenticated using an X.509 certificate.</span></span> <span data-ttu-id="f1eec-444">El enlace utilizado es un enlace simétrico donde el token de protección es una clave generada por el cliente, cifrada con la clave pública del servicio.</span><span class="sxs-lookup"><span data-stu-id="f1eec-444">The binding used is a symmetric binding with the protection token being a key generated by the client, encrypted with the public key of the service.</span></span>  
  
 <span data-ttu-id="f1eec-445">Directiva de</span><span class="sxs-lookup"><span data-stu-id="f1eec-445">Policy</span></span>  
  
 <span data-ttu-id="f1eec-446">Vea Directiva en 6.2.3 para obtener detalles sobre enlaces</span><span class="sxs-lookup"><span data-stu-id="f1eec-446">See Policy in 6.2.3 for binding details</span></span>  
  
 <span data-ttu-id="f1eec-447">Aprobar token auxiliar</span><span class="sxs-lookup"><span data-stu-id="f1eec-447">Endorsing Supporting Token</span></span>  
  
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
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="f1eec-448">Ejemplos de encabezado de seguridad: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="f1eec-448">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  

 <span data-ttu-id="f1eec-449">Solicitud</span><span class="sxs-lookup"><span data-stu-id="f1eec-449">Request</span></span>  
  
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
  
 <span data-ttu-id="f1eec-450">Response</span><span class="sxs-lookup"><span data-stu-id="f1eec-450">Response</span></span>  
  
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
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="f1eec-451">Ejemplos de encabezado de seguridad: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="f1eec-451">Security Header Examples: EncryptBeforeSign</span></span>  

 <span data-ttu-id="f1eec-452">Solicitud</span><span class="sxs-lookup"><span data-stu-id="f1eec-452">Request</span></span>  
  
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
  
 <span data-ttu-id="f1eec-453">Response</span><span class="sxs-lookup"><span data-stu-id="f1eec-453">Response</span></span>  
  
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
  
#### <a name="627-issuedtokenforcertificate"></a><span data-ttu-id="f1eec-454">6.2.7 IssuedTokenForCertificate</span><span class="sxs-lookup"><span data-stu-id="f1eec-454">6.2.7 IssuedTokenForCertificate</span></span>  

 <span data-ttu-id="f1eec-455">Con este modo de autenticación, el cliente no se autentica al servicio como tal; sino que, en su lugar, presenta un token emitido por un STS y demuestra que conoce una clave compartida.</span><span class="sxs-lookup"><span data-stu-id="f1eec-455">With this authentication mode the client does not authenticate to the service, as such, but instead presents a token issued by a STS and proves knowledge of a shared key.</span></span> <span data-ttu-id="f1eec-456">El token emitido aparece en la capa de SOAP como un token auxiliar de aprobación.</span><span class="sxs-lookup"><span data-stu-id="f1eec-456">The issued token appears at the SOAP layer as an endorsing supporting token.</span></span> <span data-ttu-id="f1eec-457">El servicio autentica al cliente utilizando un certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="f1eec-457">The service authenticates to the client using an X.509 certificate.</span></span> <span data-ttu-id="f1eec-458">El enlace utilizado es un enlace simétrico donde el token de protección es una clave generada por el cliente, cifrada con la clave pública del servicio.</span><span class="sxs-lookup"><span data-stu-id="f1eec-458">The binding used is a symmetric binding with the protection token being a key generated by the client, encrypted with the public key of the service.</span></span>  
  
 <span data-ttu-id="f1eec-459">Directiva de</span><span class="sxs-lookup"><span data-stu-id="f1eec-459">Policy</span></span>  
  
 <span data-ttu-id="f1eec-460">Vea Directiva en 6.2.3 más arriba para obtener detalles sobre enlaces</span><span class="sxs-lookup"><span data-stu-id="f1eec-460">See Policy in 6.2.3 above for binding details</span></span>  
  
 <span data-ttu-id="f1eec-461">Aprobar token auxiliar</span><span class="sxs-lookup"><span data-stu-id="f1eec-461">Endorsing Supporting Token</span></span>  
  
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
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="f1eec-462">Ejemplos de encabezado de seguridad: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="f1eec-462">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  

 <span data-ttu-id="f1eec-463">Solicitud</span><span class="sxs-lookup"><span data-stu-id="f1eec-463">Request</span></span>  
  
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
  
 <span data-ttu-id="f1eec-464">Response</span><span class="sxs-lookup"><span data-stu-id="f1eec-464">Response</span></span>  
  
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
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="f1eec-465">Ejemplos de encabezado de seguridad: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="f1eec-465">Security Header Examples: EncryptBeforeSign</span></span>  

 <span data-ttu-id="f1eec-466">Solicitud</span><span class="sxs-lookup"><span data-stu-id="f1eec-466">Request</span></span>  
  
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
  
 <span data-ttu-id="f1eec-467">Response</span><span class="sxs-lookup"><span data-stu-id="f1eec-467">Response</span></span>  
  
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
  
## <a name="63-kerberos"></a><span data-ttu-id="f1eec-468">6.3 Kerberos</span><span class="sxs-lookup"><span data-stu-id="f1eec-468">6.3 Kerberos</span></span>  

 <span data-ttu-id="f1eec-469">Con este modo de autenticación, el cliente se autentica en el servicio utilizando un tique de Kerberos.</span><span class="sxs-lookup"><span data-stu-id="f1eec-469">With this authentication mode the client authenticates to the service using a Kerberos ticket.</span></span> <span data-ttu-id="f1eec-470">Ese mismo vale también proporciona autenticación del servidor.</span><span class="sxs-lookup"><span data-stu-id="f1eec-470">That same ticket also provides server authentication.</span></span> <span data-ttu-id="f1eec-471">El enlace utilizado es un enlace simétrico con las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="f1eec-471">The binding used is a symmetric binding with the following properties;</span></span>  
  
 <span data-ttu-id="f1eec-472">Token de protección: vale de Kerberos, modo de inclusión establecido en .../IncludeToken/Once</span><span class="sxs-lookup"><span data-stu-id="f1eec-472">Protection Token: Kerberos Ticket, inclusion mode is set to .../IncludeToken/Once</span></span>  
<span data-ttu-id="f1eec-473">Protección de tokens: False</span><span class="sxs-lookup"><span data-stu-id="f1eec-473">Token Protection: False</span></span>  
  
 <span data-ttu-id="f1eec-474">Encabezado completo y firmas de cuerpo: True</span><span class="sxs-lookup"><span data-stu-id="f1eec-474">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="f1eec-475">Orden de protección: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="f1eec-475">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="f1eec-476">Cifrar firma: True</span><span class="sxs-lookup"><span data-stu-id="f1eec-476">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="f1eec-477">Directiva de</span><span class="sxs-lookup"><span data-stu-id="f1eec-477">Policy</span></span>  
  
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
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="f1eec-478">Ejemplos de encabezado de seguridad: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="f1eec-478">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  

 <span data-ttu-id="f1eec-479">Solicitud</span><span class="sxs-lookup"><span data-stu-id="f1eec-479">Request</span></span>  
  
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
  
 <span data-ttu-id="f1eec-480">Response</span><span class="sxs-lookup"><span data-stu-id="f1eec-480">Response</span></span>  
  
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
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="f1eec-481">Ejemplos de encabezado de seguridad: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="f1eec-481">Security Header Examples: EncryptBeforeSign</span></span>  

 <span data-ttu-id="f1eec-482">Solicitud</span><span class="sxs-lookup"><span data-stu-id="f1eec-482">Request</span></span>  
  
```xml  
<wsse:Security>  
TBD  
</wsse:Security>  
```  
  
 <span data-ttu-id="f1eec-483">Response</span><span class="sxs-lookup"><span data-stu-id="f1eec-483">Response</span></span>  
  
```xml  
<wsse:Security>  
TBD  
</wsse:Security>  
```  
  
#### <a name="64-issuedtoken"></a><span data-ttu-id="f1eec-484">6.4 IssuedToken</span><span class="sxs-lookup"><span data-stu-id="f1eec-484">6.4 IssuedToken</span></span>  

 <span data-ttu-id="f1eec-485">Con este modo de autenticación, el cliente no se autentica en el servicio como tal; sino que, en su lugar, presenta un token emitido por un STS y demuestra que conoce una clave compartida.</span><span class="sxs-lookup"><span data-stu-id="f1eec-485">With this authentication mode the client does not authenticate to the service, as such, rather the client presents a token issued by an STS and proves knowledge of a shared key.</span></span> <span data-ttu-id="f1eec-486">El servicio no se autentica al cliente como tal, sino que, en su lugar, el STS cifra la clave compartida como parte del token emitido, de manera que solo el servicio puede descifrar la clave.</span><span class="sxs-lookup"><span data-stu-id="f1eec-486">The service is not authenticated to the client, as such, instead the STS encrypts the shared key as part of the issued token such that only the service can decrypt the key.</span></span> <span data-ttu-id="f1eec-487">El enlace utilizado es un enlace simétrico con las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="f1eec-487">The binding used is as symmetric binding with the following properties;</span></span>  
  
 <span data-ttu-id="f1eec-488">Token de protección: token emitido, modo de inclusión establecido en .../IncludeToken/AlwaysToRecipient</span><span class="sxs-lookup"><span data-stu-id="f1eec-488">Protection Token: Issued Token, inclusion mode is set to .../IncludeToken/AlwaysToRecipient</span></span>  
<span data-ttu-id="f1eec-489">Protección de tokens: False</span><span class="sxs-lookup"><span data-stu-id="f1eec-489">Token Protection: False</span></span>  
  
 <span data-ttu-id="f1eec-490">Encabezado completo y firmas de cuerpo: True</span><span class="sxs-lookup"><span data-stu-id="f1eec-490">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="f1eec-491">Orden de protección: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="f1eec-491">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="f1eec-492">Cifrar firma: True</span><span class="sxs-lookup"><span data-stu-id="f1eec-492">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="f1eec-493">Directiva de</span><span class="sxs-lookup"><span data-stu-id="f1eec-493">Policy</span></span>  
  
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
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="f1eec-494">Ejemplos de encabezado de seguridad: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="f1eec-494">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  

 <span data-ttu-id="f1eec-495">Solicitud</span><span class="sxs-lookup"><span data-stu-id="f1eec-495">Request</span></span>  
  
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
  
 <span data-ttu-id="f1eec-496">Response</span><span class="sxs-lookup"><span data-stu-id="f1eec-496">Response</span></span>  
  
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
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="f1eec-497">Ejemplos de encabezado de seguridad: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="f1eec-497">Security Header Examples: EncryptBeforeSign</span></span>  

 <span data-ttu-id="f1eec-498">Solicitud</span><span class="sxs-lookup"><span data-stu-id="f1eec-498">Request</span></span>  
  
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
  
 <span data-ttu-id="f1eec-499">Response</span><span class="sxs-lookup"><span data-stu-id="f1eec-499">Response</span></span>  
  
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
  
### <a name="65-using-sslnegotiated-for-service-authentication"></a><span data-ttu-id="f1eec-500">6.5 Uso de SslNegotiated para la autenticación de servicio</span><span class="sxs-lookup"><span data-stu-id="f1eec-500">6.5 Using SslNegotiated for Service Authentication</span></span>  

 <span data-ttu-id="f1eec-501">En esta sección se describe un grupo de modos de autenticación que utilizan un enlace simétrico donde el token de protección es un token de contexto de seguridad por WS-SecureConversation (WS SC), cuyo valor de clave se negocia ejecutando el protocolo TLS sobre mensajes de RST/RSTR de WS-Trust (WS-T).</span><span class="sxs-lookup"><span data-stu-id="f1eec-501">This section describes a group of authentication modes that use a symmetric binding with the protection token being a Security Context Token per WS-SecureConversation (WS-SC) whose key value is negotiated by executing the TLS protocol over WS-Trust (WS-T) RST/RSTR messages.</span></span> <span data-ttu-id="f1eec-502">En TLSNEGO se describen los detalles de la implementación del protocolo de enlace de TLS mediante WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="f1eec-502">Details of the TLS handshake implementation using WS-Trust are described in TLSNEGO.</span></span> <span data-ttu-id="f1eec-503">Aquí en los ejemplos de mensajes supondremos que SCT con un contexto de seguridad asociado ya se establece a través de un protocolo de enlace.</span><span class="sxs-lookup"><span data-stu-id="f1eec-503">Here in the message examples we will assume that SCT with an associated security context is already established through a handshake.</span></span>  
  
 <span data-ttu-id="f1eec-504">El enlace utilizado es un enlace simétrico con las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="f1eec-504">The binding used is a symmetric binding with the following properties;</span></span>  
  
 <span data-ttu-id="f1eec-505">Token de protección: SslContextToken, modo de inclusión establecido en .../IncludeToken/Never</span><span class="sxs-lookup"><span data-stu-id="f1eec-505">Protection Token: SslContextToken, inclusion mode is set to .../IncludeToken/Never</span></span>  
<span data-ttu-id="f1eec-506">Protección de tokens: False</span><span class="sxs-lookup"><span data-stu-id="f1eec-506">Token Protection: False</span></span>  
  
 <span data-ttu-id="f1eec-507">Encabezado completo y firmas de cuerpo: True</span><span class="sxs-lookup"><span data-stu-id="f1eec-507">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="f1eec-508">Orden de protección: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="f1eec-508">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="f1eec-509">Cifrar firma: True</span><span class="sxs-lookup"><span data-stu-id="f1eec-509">Encrypt Signature: True</span></span>  
  
#### <a name="651-policy-for-sslnegotiated-service-authentication"></a><span data-ttu-id="f1eec-510">6.5.1 Directiva para la autenticación de servicio SslNegotiated</span><span class="sxs-lookup"><span data-stu-id="f1eec-510">6.5.1 Policy for SslNegotiated service authentication</span></span>  

 <span data-ttu-id="f1eec-511">La directiva para todos los modos de autenticación de esta sección es similar y solo difieren en los tokens auxiliares firmados o aprobados empleados.</span><span class="sxs-lookup"><span data-stu-id="f1eec-511">Policy for all authentication modes in this section are similar and differ only by specific signed supporting or endorsing tokens used.</span></span>  
  
```xml  
<wsp:Policy wsu:Id='SslNegotiated_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:SymmetricBinding>  
        <wsp:Policy>  
          <sp:ProtectionToken>  
            <wsp:Policy>  
              <mssp:SslContextToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient'>  
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
  
#### <a name="652-anonymousforsslnegotiated"></a><span data-ttu-id="f1eec-512">6.5.2 AnonymousForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="f1eec-512">6.5.2 AnonymousForSslNegotiated</span></span>  

 <span data-ttu-id="f1eec-513">Con este modo de autenticación, el cliente es anónimo y el servicio se autentica utilizando un certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="f1eec-513">With this authentication mode the client is anonymous and the service is authenticated using an X.509 certificate.</span></span> <span data-ttu-id="f1eec-514">El enlace utilizado es una instancia de enlace simétrico tal y como se describe en 6.5.1 más arriba.</span><span class="sxs-lookup"><span data-stu-id="f1eec-514">The binding used is an instance of symmetric binding as described in 6.5.1 above.</span></span>  
  
 <span data-ttu-id="f1eec-515">Directiva de</span><span class="sxs-lookup"><span data-stu-id="f1eec-515">Policy</span></span>  
  
 <span data-ttu-id="f1eec-516">Vea Directiva en 6.5.1 más arriba para obtener detalles sobre enlaces.</span><span class="sxs-lookup"><span data-stu-id="f1eec-516">See Policy in 6.5.1 above for binding details.</span></span>  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="f1eec-517">Ejemplos de encabezado de seguridad: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="f1eec-517">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  

 <span data-ttu-id="f1eec-518">Solicitud</span><span class="sxs-lookup"><span data-stu-id="f1eec-518">Request</span></span>  
  
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
  
 <span data-ttu-id="f1eec-519">Response</span><span class="sxs-lookup"><span data-stu-id="f1eec-519">Response</span></span>  
  
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
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="f1eec-520">Ejemplos de encabezado de seguridad: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="f1eec-520">Security Header Examples: EncryptBeforeSign</span></span>  

 <span data-ttu-id="f1eec-521">Solicitud</span><span class="sxs-lookup"><span data-stu-id="f1eec-521">Request</span></span>  
  
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
  
 <span data-ttu-id="f1eec-522">Response</span><span class="sxs-lookup"><span data-stu-id="f1eec-522">Response</span></span>  
  
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
  
#### <a name="653-usernameforsslnegotiated"></a><span data-ttu-id="f1eec-523">6.5.3 UserNameForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="f1eec-523">6.5.3 UserNameForSslNegotiated</span></span>  

 <span data-ttu-id="f1eec-524">Con este modo de autenticación el cliente se autentica el servicio utilizando un token de nombre de usuario que aparece en la capa SOAP como un token auxiliar firmado.</span><span class="sxs-lookup"><span data-stu-id="f1eec-524">With this authentication mode the client is authenticates using a Username Token which appears at the SOAP layer as a signed supporting token.</span></span> <span data-ttu-id="f1eec-525">La autenticación del servicio se realiza mediante un certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="f1eec-525">The service is authenticated using an X.509 certificate.</span></span> <span data-ttu-id="f1eec-526">El enlace utilizado es una instancia de enlace simétrico tal y como se describe en 6.5.1.</span><span class="sxs-lookup"><span data-stu-id="f1eec-526">The binding used is an instance of symmetric binding as described in 6.5.1.</span></span>  
  
 <span data-ttu-id="f1eec-527">Directiva de</span><span class="sxs-lookup"><span data-stu-id="f1eec-527">Policy</span></span>  
  
 <span data-ttu-id="f1eec-528">Vea la sección 6.5.1 anterior para obtener detalles sobre los enlaces</span><span class="sxs-lookup"><span data-stu-id="f1eec-528">See section 6.5.1 above for binding details</span></span>  
  
 <span data-ttu-id="f1eec-529">Token auxiliar firmado</span><span class="sxs-lookup"><span data-stu-id="f1eec-529">Signed Supporting Token</span></span>  
  
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
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="f1eec-530">Ejemplos de encabezado de seguridad: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="f1eec-530">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  

 <span data-ttu-id="f1eec-531">Solicitud</span><span class="sxs-lookup"><span data-stu-id="f1eec-531">Request</span></span>  
  
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
  
 <span data-ttu-id="f1eec-532">Response</span><span class="sxs-lookup"><span data-stu-id="f1eec-532">Response</span></span>  
  
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
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="f1eec-533">Ejemplos de encabezado de seguridad: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="f1eec-533">Security Header Examples: EncryptBeforeSign</span></span>  

 <span data-ttu-id="f1eec-534">Solicitud</span><span class="sxs-lookup"><span data-stu-id="f1eec-534">Request</span></span>  
  
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
  
 <span data-ttu-id="f1eec-535">Response</span><span class="sxs-lookup"><span data-stu-id="f1eec-535">Response</span></span>  
  
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
  
#### <a name="654-issuedtokenforsslnegotiated"></a><span data-ttu-id="f1eec-536">6.5.4 IssuedTokenForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="f1eec-536">6.5.4 IssuedTokenForSslNegotiated</span></span>  

 <span data-ttu-id="f1eec-537">Con este modo de autenticación, el cliente no se autentica al servicio como tal; sino que, en su lugar, presenta un token emitido por un STS y demuestra que conoce una clave compartida.</span><span class="sxs-lookup"><span data-stu-id="f1eec-537">With this authentication mode the client does not authenticate to the service, as such, but instead presents a token issued by an STS and proves knowledge of a shared key.</span></span> <span data-ttu-id="f1eec-538">El token emitido aparece en la capa de SOAP como un token auxiliar de aprobación.</span><span class="sxs-lookup"><span data-stu-id="f1eec-538">The issued token appears at the SOAP layer as an endorsing supporting token.</span></span> <span data-ttu-id="f1eec-539">La autenticación del servicio se realiza mediante un certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="f1eec-539">The service is authenticated using an X.509 certificate.</span></span> <span data-ttu-id="f1eec-540">El enlace utilizado es una instancia de enlace simétrico tal y como se describe en 6.5.1 más arriba.</span><span class="sxs-lookup"><span data-stu-id="f1eec-540">The binding used is an instance of symmetric binding as described in 6.5.1 above.</span></span>  
  
 <span data-ttu-id="f1eec-541">Directiva de</span><span class="sxs-lookup"><span data-stu-id="f1eec-541">Policy</span></span>  
  
 <span data-ttu-id="f1eec-542">Vea la sección 6.5.1 anterior para obtener detalles sobre los enlaces</span><span class="sxs-lookup"><span data-stu-id="f1eec-542">See section 6.5.1 above for binding details</span></span>  
  
 <span data-ttu-id="f1eec-543">Aprobar token auxiliar</span><span class="sxs-lookup"><span data-stu-id="f1eec-543">Endorsing Supporting Token</span></span>  
  
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
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="f1eec-544">Ejemplos de encabezado de seguridad: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="f1eec-544">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  

 <span data-ttu-id="f1eec-545">Solicitud</span><span class="sxs-lookup"><span data-stu-id="f1eec-545">Request</span></span>  
  
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
  
 <span data-ttu-id="f1eec-546">Response</span><span class="sxs-lookup"><span data-stu-id="f1eec-546">Response</span></span>  
  
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
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="f1eec-547">Ejemplos de encabezado de seguridad: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="f1eec-547">Security Header Examples: EncryptBeforeSign</span></span>  

 <span data-ttu-id="f1eec-548">Solicitud</span><span class="sxs-lookup"><span data-stu-id="f1eec-548">Request</span></span>  
  
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
  
 <span data-ttu-id="f1eec-549">Response</span><span class="sxs-lookup"><span data-stu-id="f1eec-549">Response</span></span>  
  
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
  
#### <a name="655-mutualsslnegotiated"></a><span data-ttu-id="f1eec-550">6.5.5 MutualSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="f1eec-550">6.5.5 MutualSslNegotiated</span></span>  

 <span data-ttu-id="f1eec-551">Con este modo de autenticación, el cliente y el servicio autentican utilizando los certificados X.509.</span><span class="sxs-lookup"><span data-stu-id="f1eec-551">With this authentication mode the client and the service authenticate using X.509 certificates.</span></span> <span data-ttu-id="f1eec-552">El enlace utilizado es una instancia de enlace simétrico tal y como se describe en 6.5.1 más arriba.</span><span class="sxs-lookup"><span data-stu-id="f1eec-552">The binding used is an instance of symmetric binding as described in 6.5.1 above.</span></span>  
  
 <span data-ttu-id="f1eec-553">Directiva de</span><span class="sxs-lookup"><span data-stu-id="f1eec-553">Policy</span></span>  
  
 <span data-ttu-id="f1eec-554">Vea la sección 6.5.1 anterior para obtener detalles sobre los enlaces</span><span class="sxs-lookup"><span data-stu-id="f1eec-554">See section 6.5.1 above for binding details</span></span>  
  
 <span data-ttu-id="f1eec-555">Aprobar token auxiliar</span><span class="sxs-lookup"><span data-stu-id="f1eec-555">Endorsing Supporting Token</span></span>  
  
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
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="f1eec-556">Ejemplos de encabezado de seguridad: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="f1eec-556">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  

 <span data-ttu-id="f1eec-557">Solicitud</span><span class="sxs-lookup"><span data-stu-id="f1eec-557">Request</span></span>  
  
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
  
 <span data-ttu-id="f1eec-558">Response</span><span class="sxs-lookup"><span data-stu-id="f1eec-558">Response</span></span>  
  
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
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="f1eec-559">Ejemplos de encabezado de seguridad: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="f1eec-559">Security Header Examples: EncryptBeforeSign</span></span>  

 <span data-ttu-id="f1eec-560">Solicitud</span><span class="sxs-lookup"><span data-stu-id="f1eec-560">Request</span></span>  
  
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
  
 <span data-ttu-id="f1eec-561">Response</span><span class="sxs-lookup"><span data-stu-id="f1eec-561">Response</span></span>  
  
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
  
### <a name="66-sspinegotiated"></a><span data-ttu-id="f1eec-562">6.6 SspiNegotiated</span><span class="sxs-lookup"><span data-stu-id="f1eec-562">6.6 SspiNegotiated</span></span>  

 <span data-ttu-id="f1eec-563">Con este modo de autenticación, se usa un protocolo de negociación para realizar la autenticación del cliente y del servidor.</span><span class="sxs-lookup"><span data-stu-id="f1eec-563">With this authentication mode a negotiation protocol is used to perform client and server authentication.</span></span> <span data-ttu-id="f1eec-564">Se utiliza Kerberos si es posible; de lo contrario, se utiliza NTLM.</span><span class="sxs-lookup"><span data-stu-id="f1eec-564">Kerberos is used if possible, otherwise NTLM.</span></span> <span data-ttu-id="f1eec-565">El enlace utilizado es un enlace simétrico con las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="f1eec-565">The binding used is a symmetric binding with the following properties;</span></span>  
  
 <span data-ttu-id="f1eec-566">Token de protección: SpnegoContextToken, modo de inclusión establecido en .../IncludeToken/AlwaysToRecipient</span><span class="sxs-lookup"><span data-stu-id="f1eec-566">Protection Token: SpnegoContextToken, inclusion mode is set to .../IncludeToken/AlwaysToRecipient</span></span>  
<span data-ttu-id="f1eec-567">Protección de tokens: False</span><span class="sxs-lookup"><span data-stu-id="f1eec-567">Token Protection: False</span></span>  
  
 <span data-ttu-id="f1eec-568">Encabezado completo y firmas de cuerpo: True</span><span class="sxs-lookup"><span data-stu-id="f1eec-568">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="f1eec-569">Orden de protección: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="f1eec-569">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="f1eec-570">Cifrar firma: True</span><span class="sxs-lookup"><span data-stu-id="f1eec-570">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="f1eec-571">Directiva de</span><span class="sxs-lookup"><span data-stu-id="f1eec-571">Policy</span></span>  
  
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
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="f1eec-572">Ejemplos de encabezado de seguridad: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="f1eec-572">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  

 <span data-ttu-id="f1eec-573">Solicitud</span><span class="sxs-lookup"><span data-stu-id="f1eec-573">Request</span></span>  
  
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
  
 <span data-ttu-id="f1eec-574">Response</span><span class="sxs-lookup"><span data-stu-id="f1eec-574">Response</span></span>  
  
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
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="f1eec-575">Ejemplos de encabezado de seguridad: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="f1eec-575">Security Header Examples: EncryptBeforeSign</span></span>  

 <span data-ttu-id="f1eec-576">Solicitud</span><span class="sxs-lookup"><span data-stu-id="f1eec-576">Request</span></span>  
  
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
  
 <span data-ttu-id="f1eec-577">Response</span><span class="sxs-lookup"><span data-stu-id="f1eec-577">Response</span></span>  
  
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
  
### <a name="67-secureconversation"></a><span data-ttu-id="f1eec-578">6.7 SecureConversation</span><span class="sxs-lookup"><span data-stu-id="f1eec-578">6.7 SecureConversation</span></span>  

 <span data-ttu-id="f1eec-579">El enlace utilizado es un enlace simétrico donde el token de protección es un SCT por WS-SecureConversation (WS SC).</span><span class="sxs-lookup"><span data-stu-id="f1eec-579">The binding used is a symmetric binding with the protection token being a SCT per WS-SecureConversation (WS-SC).</span></span> <span data-ttu-id="f1eec-580">El SCT se negocia mediante WS-Trust (WS-Trust) o WS-SecureConversation (WS-SC) según un enlace anidado, que es en sí mismo un enlace simétrico que usa un protocolo de negociación.</span><span class="sxs-lookup"><span data-stu-id="f1eec-580">The SCT is negotiated using WS-Trust (WS-Trust) or WS-SecureConversation (WS-SC) according to a nested binding, which is itself a symmetric binding that uses a negotiation protocol.</span></span> <span data-ttu-id="f1eec-581">El protocolo de negociación utilizará Kerberos para realizar la autenticación de cliente y servidor si es posible.</span><span class="sxs-lookup"><span data-stu-id="f1eec-581">The negotiation protocol will use Kerberos to perform client and server authentication if possible.</span></span> <span data-ttu-id="f1eec-582">Si no se puede utilizar Kerberos, se volverá a NTLM.</span><span class="sxs-lookup"><span data-stu-id="f1eec-582">If Kerberos cannot be used, it will fall back to NTLM.</span></span>  
  
 <span data-ttu-id="f1eec-583">Directiva de</span><span class="sxs-lookup"><span data-stu-id="f1eec-583">Policy</span></span>  
  
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
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="f1eec-584">Ejemplos de encabezado de seguridad: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="f1eec-584">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  

 <span data-ttu-id="f1eec-585">Solicitud</span><span class="sxs-lookup"><span data-stu-id="f1eec-585">Request</span></span>  
  
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
  
 <span data-ttu-id="f1eec-586">Response</span><span class="sxs-lookup"><span data-stu-id="f1eec-586">Response</span></span>  
  
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
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="f1eec-587">Ejemplos de encabezado de seguridad: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="f1eec-587">Security Header Examples: EncryptBeforeSign</span></span>  

 <span data-ttu-id="f1eec-588">Solicitud</span><span class="sxs-lookup"><span data-stu-id="f1eec-588">Request</span></span>  
  
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
  
 <span data-ttu-id="f1eec-589">Response</span><span class="sxs-lookup"><span data-stu-id="f1eec-589">Response</span></span>  
  
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
