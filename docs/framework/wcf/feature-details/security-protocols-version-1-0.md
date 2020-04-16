---
title: Protocolos de seguridad versión 1.0
ms.date: 03/30/2017
ms.assetid: ee3402d2-1076-410b-a3cb-fae0372bd7af
ms.openlocfilehash: 0b86d870350d8728134cd2b42bbeb232183535bc
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463805"
---
# <a name="security-protocols-version-10"></a><span data-ttu-id="78cff-102">Protocolos de seguridad versión 1.0</span><span class="sxs-lookup"><span data-stu-id="78cff-102">Security Protocols version 1.0</span></span>
<span data-ttu-id="78cff-103">Los protocolos de seguridad de servicios Web proporcionan mecanismos de seguridad de servicios Web que cubren todos los requisitos de seguridad de mensajería para empresas existentes.</span><span class="sxs-lookup"><span data-stu-id="78cff-103">The Web Services Security Protocols provide Web services security mechanisms that cover all existing enterprise messaging security requirements.</span></span> <span data-ttu-id="78cff-104">En esta sección se describen los detalles de Windows Communication <xref:System.ServiceModel.Channels.SecurityBindingElement>Foundation (WCF) versión 1.0 (implementados en el ) para los siguientes protocolos de seguridad de servicios web.</span><span class="sxs-lookup"><span data-stu-id="78cff-104">This section describes the Windows Communication Foundation (WCF) version 1.0 details (implemented in the <xref:System.ServiceModel.Channels.SecurityBindingElement>) for the following Web services security protocols.</span></span>  
  
|<span data-ttu-id="78cff-105">Especificación/documento</span><span class="sxs-lookup"><span data-stu-id="78cff-105">Specification/Document</span></span>|<span data-ttu-id="78cff-106">Vínculo</span><span class="sxs-lookup"><span data-stu-id="78cff-106">Link</span></span>|  
|-|-|  
|<span data-ttu-id="78cff-107">WSS: Message Security 1,0 de SOAP</span><span class="sxs-lookup"><span data-stu-id="78cff-107">WSS: SOAP Message Security 1.0</span></span>|<https://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-soap-message-security-1.0.pdf>|
|<span data-ttu-id="78cff-108">WSS: Token Profile 1.0 de Username</span><span class="sxs-lookup"><span data-stu-id="78cff-108">WSS: Username Token Profile 1.0</span></span>|<https://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-username-token-profile-1.0.pdf>|
|<span data-ttu-id="78cff-109">WSS: Token Profile 1,0 de X509</span><span class="sxs-lookup"><span data-stu-id="78cff-109">WSS: X509 Token Profile 1.0</span></span>|<https://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-x509-token-profile-1.0.pdf>|
|<span data-ttu-id="78cff-110">WSS: Token Profile 1.1 de SAML 1,0</span><span class="sxs-lookup"><span data-stu-id="78cff-110">WSS: SAML 1.1 Token Profile 1.0</span></span>|<https://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.0.pdf>|
|<span data-ttu-id="78cff-111">WSS: Message Security 1.1 de SOAP</span><span class="sxs-lookup"><span data-stu-id="78cff-111">WSS: SOAP Message Security 1.1</span></span>|<https://www.oasis-open.org/committees/download.php/16790/wss-v1.1-spec-os-SOAPMessageSecurity.pdf>|
|<span data-ttu-id="78cff-112">WSS: Token Profile 1.1 de Username</span><span class="sxs-lookup"><span data-stu-id="78cff-112">WSS Username Token Profile 1.1</span></span>|<https://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-username-token-profile-1.0.pdf>|
|<span data-ttu-id="78cff-113">WSS: Token Profile 1,1 de X.509</span><span class="sxs-lookup"><span data-stu-id="78cff-113">WSS: X.509 Token Profile 1.1</span></span>|<https://www.oasis-open.org/committees/download.php/16785/wss-v1.1-spec-os-x509TokenProfile.pdf>|
|<span data-ttu-id="78cff-114">WSS: Token Profile 1.1 de Kerberos</span><span class="sxs-lookup"><span data-stu-id="78cff-114">WSS: Kerberos Token Profile 1.1</span></span>|<https://www.oasis-open.org/committees/download.php/16788/wss-v1.1-spec-os-KerberosTokenProfile.pdf>|
|<span data-ttu-id="78cff-115">WSS: Token Profile 1.1 de SAML 1.1</span><span class="sxs-lookup"><span data-stu-id="78cff-115">WSS: SAML 1.1 Token Profile 1.1</span></span>|<https://www.oasis-open.org/committees/download.php/16768/wss-v1.1-spec-os-SAMLTokenProfile.pdf>|
|<span data-ttu-id="78cff-116">WS-Secure Conversation</span><span class="sxs-lookup"><span data-stu-id="78cff-116">WS-Secure Conversation</span></span>|<https://specs.xmlsoap.org/ws/2005/02/sc/WS-SecureConversation.pdf>|
|<span data-ttu-id="78cff-117">WS-Trust</span><span class="sxs-lookup"><span data-stu-id="78cff-117">WS-Trust</span></span>|<https://specs.xmlsoap.org/ws/2005/02/trust/ws-trust.pdf>|
|<span data-ttu-id="78cff-118">Nota de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="78cff-118">Application Note:</span></span><br /><br /> <span data-ttu-id="78cff-119">Uso de WS-Trust para protocolo de enlace TLS</span><span class="sxs-lookup"><span data-stu-id="78cff-119">Using WS-Trust for TLS Handshake</span></span>|<span data-ttu-id="78cff-120">Para su publicación</span><span class="sxs-lookup"><span data-stu-id="78cff-120">To be published</span></span>|  
|<span data-ttu-id="78cff-121">Nota de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="78cff-121">Application Note:</span></span><br /><br /> <span data-ttu-id="78cff-122">Uso de WS-Trust para SPNEGO</span><span class="sxs-lookup"><span data-stu-id="78cff-122">Using WS-Trust for SPNEGO</span></span>|<span data-ttu-id="78cff-123">Para su publicación</span><span class="sxs-lookup"><span data-stu-id="78cff-123">To be published</span></span>|  
|<span data-ttu-id="78cff-124">Nota de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="78cff-124">Application Note:</span></span><br /><br /> <span data-ttu-id="78cff-125">Referencias e identidad de extremos de direccionamiento de servicios Web</span><span class="sxs-lookup"><span data-stu-id="78cff-125">Web Services Addressing Endpoint References And Identity</span></span>|<span data-ttu-id="78cff-126">Para su publicación</span><span class="sxs-lookup"><span data-stu-id="78cff-126">To be published</span></span>|  
|<span data-ttu-id="78cff-127">WS-SecurityPolicy 1.1</span><span class="sxs-lookup"><span data-stu-id="78cff-127">WS-SecurityPolicy 1.1</span></span><br /><br /> <span data-ttu-id="78cff-128">(2005/07)</span><span class="sxs-lookup"><span data-stu-id="78cff-128">(2005/07)</span></span>|<https://specs.xmlsoap.org/ws/2005/07/securitypolicy/ws-securitypolicy.pdf><br /><br /> <span data-ttu-id="78cff-129">enmendada por [las erratas](https://lists.oasis-open.org/archives/ws-sx/200512/msg00017.html) presentadas al Comité Técnico de OASIS WS-SX</span><span class="sxs-lookup"><span data-stu-id="78cff-129">as amended by [errata](https://lists.oasis-open.org/archives/ws-sx/200512/msg00017.html) submitted to OASIS WS-SX Technical Committee</span></span> |  
  
 <span data-ttu-id="78cff-130">WCF, versión 1, proporciona 17 modos de autenticación que se pueden usar como base para la configuración de seguridad de servicios web.</span><span class="sxs-lookup"><span data-stu-id="78cff-130">WCF, version 1, provides 17 authentication modes that can be used as the basis for Web services security configuration.</span></span> <span data-ttu-id="78cff-131">Cada modo se optimiza para un conjunto común de requisitos de implementación, como:</span><span class="sxs-lookup"><span data-stu-id="78cff-131">Each mode is optimized for a common set of deployment requirements, such as:</span></span>  
  
- <span data-ttu-id="78cff-132">Credenciales utilizadas para autenticar cliente y servicio.</span><span class="sxs-lookup"><span data-stu-id="78cff-132">Credentials used to authenticate client and service.</span></span>  
  
- <span data-ttu-id="78cff-133">Mecanismos de protección de seguridad de transporte o mensaje.</span><span class="sxs-lookup"><span data-stu-id="78cff-133">Message or transport security protection mechanisms.</span></span>  
  
- <span data-ttu-id="78cff-134">Patrones de intercambio de mensajes.</span><span class="sxs-lookup"><span data-stu-id="78cff-134">Message exchange patterns.</span></span>  
  
|<span data-ttu-id="78cff-135">Modo de autenticación</span><span class="sxs-lookup"><span data-stu-id="78cff-135">Authentication Mode</span></span>|<span data-ttu-id="78cff-136">Autenticación de clientes</span><span class="sxs-lookup"><span data-stu-id="78cff-136">Client Authentication</span></span>|<span data-ttu-id="78cff-137">Autenticación de servidor</span><span class="sxs-lookup"><span data-stu-id="78cff-137">Server Authentication</span></span>|<span data-ttu-id="78cff-138">Mode</span><span class="sxs-lookup"><span data-stu-id="78cff-138">Mode</span></span>|  
|-------------------------|---------------------------|---------------------------|----------|  
|<span data-ttu-id="78cff-139">UserNameOverTransport</span><span class="sxs-lookup"><span data-stu-id="78cff-139">UserNameOverTransport</span></span>|<span data-ttu-id="78cff-140">Nombre de usuario/contraseña</span><span class="sxs-lookup"><span data-stu-id="78cff-140">User name/password</span></span>|<span data-ttu-id="78cff-141">X509</span><span class="sxs-lookup"><span data-stu-id="78cff-141">X509</span></span>|<span data-ttu-id="78cff-142">Transporte</span><span class="sxs-lookup"><span data-stu-id="78cff-142">Transport</span></span>|  
|<span data-ttu-id="78cff-143">CertificateOverTransport</span><span class="sxs-lookup"><span data-stu-id="78cff-143">CertificateOverTransport</span></span>|<span data-ttu-id="78cff-144">X509</span><span class="sxs-lookup"><span data-stu-id="78cff-144">X509</span></span>|<span data-ttu-id="78cff-145">X509</span><span class="sxs-lookup"><span data-stu-id="78cff-145">X509</span></span>|<span data-ttu-id="78cff-146">Transporte</span><span class="sxs-lookup"><span data-stu-id="78cff-146">Transport</span></span>|  
|<span data-ttu-id="78cff-147">KerberosOverTransport</span><span class="sxs-lookup"><span data-stu-id="78cff-147">KerberosOverTransport</span></span>|<span data-ttu-id="78cff-148">Windows</span><span class="sxs-lookup"><span data-stu-id="78cff-148">Windows</span></span>|<span data-ttu-id="78cff-149">X509</span><span class="sxs-lookup"><span data-stu-id="78cff-149">X509</span></span>|<span data-ttu-id="78cff-150">Transporte</span><span class="sxs-lookup"><span data-stu-id="78cff-150">Transport</span></span>|  
|<span data-ttu-id="78cff-151">IssuedTokenOverTransport</span><span class="sxs-lookup"><span data-stu-id="78cff-151">IssuedTokenOverTransport</span></span>|<span data-ttu-id="78cff-152">Federado</span><span class="sxs-lookup"><span data-stu-id="78cff-152">Federated</span></span>|<span data-ttu-id="78cff-153">X509</span><span class="sxs-lookup"><span data-stu-id="78cff-153">X509</span></span>|<span data-ttu-id="78cff-154">Transporte</span><span class="sxs-lookup"><span data-stu-id="78cff-154">Transport</span></span>|  
|<span data-ttu-id="78cff-155">SspiNegotiatedOverTransport</span><span class="sxs-lookup"><span data-stu-id="78cff-155">SspiNegotiatedOverTransport</span></span>|<span data-ttu-id="78cff-156">Windows SSPI negociado</span><span class="sxs-lookup"><span data-stu-id="78cff-156">Windows Sspi Negotiated</span></span>|<span data-ttu-id="78cff-157">Windows SSPI negociado</span><span class="sxs-lookup"><span data-stu-id="78cff-157">Windows Sspi Negotiated</span></span>|<span data-ttu-id="78cff-158">Transporte</span><span class="sxs-lookup"><span data-stu-id="78cff-158">Transport</span></span>|  
|<span data-ttu-id="78cff-159">AnonymousForCertificate</span><span class="sxs-lookup"><span data-stu-id="78cff-159">AnonymousForCertificate</span></span>|<span data-ttu-id="78cff-160">None</span><span class="sxs-lookup"><span data-stu-id="78cff-160">None</span></span>|<span data-ttu-id="78cff-161">X509</span><span class="sxs-lookup"><span data-stu-id="78cff-161">X509</span></span>|<span data-ttu-id="78cff-162">Message</span><span class="sxs-lookup"><span data-stu-id="78cff-162">Message</span></span>|  
|<span data-ttu-id="78cff-163">UserNameForCertificate</span><span class="sxs-lookup"><span data-stu-id="78cff-163">UserNameForCertificate</span></span>|<span data-ttu-id="78cff-164">Nombre de usuario/contraseña</span><span class="sxs-lookup"><span data-stu-id="78cff-164">User name/password</span></span>|<span data-ttu-id="78cff-165">X509</span><span class="sxs-lookup"><span data-stu-id="78cff-165">X509</span></span>|<span data-ttu-id="78cff-166">Message</span><span class="sxs-lookup"><span data-stu-id="78cff-166">Message</span></span>|  
|<span data-ttu-id="78cff-167">MutualCertificate</span><span class="sxs-lookup"><span data-stu-id="78cff-167">MutualCertificate</span></span>|<span data-ttu-id="78cff-168">X509</span><span class="sxs-lookup"><span data-stu-id="78cff-168">X509</span></span>|<span data-ttu-id="78cff-169">X509</span><span class="sxs-lookup"><span data-stu-id="78cff-169">X509</span></span>|<span data-ttu-id="78cff-170">Message</span><span class="sxs-lookup"><span data-stu-id="78cff-170">Message</span></span>|  
|<span data-ttu-id="78cff-171">MutualCertificateDuplex</span><span class="sxs-lookup"><span data-stu-id="78cff-171">MutualCertificateDuplex</span></span>|<span data-ttu-id="78cff-172">X509</span><span class="sxs-lookup"><span data-stu-id="78cff-172">X509</span></span>|<span data-ttu-id="78cff-173">X509</span><span class="sxs-lookup"><span data-stu-id="78cff-173">X509</span></span>|<span data-ttu-id="78cff-174">Message</span><span class="sxs-lookup"><span data-stu-id="78cff-174">Message</span></span>|  
|<span data-ttu-id="78cff-175">IssuedTokenForCertificate</span><span class="sxs-lookup"><span data-stu-id="78cff-175">IssuedTokenForCertificate</span></span>|<span data-ttu-id="78cff-176">Federado</span><span class="sxs-lookup"><span data-stu-id="78cff-176">Federated</span></span>|<span data-ttu-id="78cff-177">X509</span><span class="sxs-lookup"><span data-stu-id="78cff-177">X509</span></span>|<span data-ttu-id="78cff-178">Message</span><span class="sxs-lookup"><span data-stu-id="78cff-178">Message</span></span>|  
|<span data-ttu-id="78cff-179">Kerberos</span><span class="sxs-lookup"><span data-stu-id="78cff-179">Kerberos</span></span>|<span data-ttu-id="78cff-180">Windows</span><span class="sxs-lookup"><span data-stu-id="78cff-180">Windows</span></span>|<span data-ttu-id="78cff-181">Windows</span><span class="sxs-lookup"><span data-stu-id="78cff-181">Windows</span></span>|<span data-ttu-id="78cff-182">Message</span><span class="sxs-lookup"><span data-stu-id="78cff-182">Message</span></span>|  
|<span data-ttu-id="78cff-183">IssuedToken</span><span class="sxs-lookup"><span data-stu-id="78cff-183">IssuedToken</span></span>|<span data-ttu-id="78cff-184">Federado</span><span class="sxs-lookup"><span data-stu-id="78cff-184">Federated</span></span>|<span data-ttu-id="78cff-185">Federado</span><span class="sxs-lookup"><span data-stu-id="78cff-185">Federated</span></span>|<span data-ttu-id="78cff-186">Message</span><span class="sxs-lookup"><span data-stu-id="78cff-186">Message</span></span>|  
|<span data-ttu-id="78cff-187">SspiNegotiated</span><span class="sxs-lookup"><span data-stu-id="78cff-187">SspiNegotiated</span></span>|<span data-ttu-id="78cff-188">Windows SSPI negociado</span><span class="sxs-lookup"><span data-stu-id="78cff-188">Windows Sspi Negotiated</span></span>|<span data-ttu-id="78cff-189">Windows SSPI negociado</span><span class="sxs-lookup"><span data-stu-id="78cff-189">Windows Sspi Negotiated</span></span>|<span data-ttu-id="78cff-190">Message</span><span class="sxs-lookup"><span data-stu-id="78cff-190">Message</span></span>|  
|<span data-ttu-id="78cff-191">AnonymousForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="78cff-191">AnonymousForSslNegotiated</span></span>|<span data-ttu-id="78cff-192">None</span><span class="sxs-lookup"><span data-stu-id="78cff-192">None</span></span>|<span data-ttu-id="78cff-193">X509, TLS-Nego</span><span class="sxs-lookup"><span data-stu-id="78cff-193">X509, TLS-Nego</span></span>|<span data-ttu-id="78cff-194">Message</span><span class="sxs-lookup"><span data-stu-id="78cff-194">Message</span></span>|  
|<span data-ttu-id="78cff-195">UserNameForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="78cff-195">UserNameForSslNegotiated</span></span>|<span data-ttu-id="78cff-196">Nombre de usuario/contraseña</span><span class="sxs-lookup"><span data-stu-id="78cff-196">User name/password</span></span>|<span data-ttu-id="78cff-197">X509, TLS-Nego</span><span class="sxs-lookup"><span data-stu-id="78cff-197">X509, TLS-Nego</span></span>|<span data-ttu-id="78cff-198">Message</span><span class="sxs-lookup"><span data-stu-id="78cff-198">Message</span></span>|  
|<span data-ttu-id="78cff-199">MutualSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="78cff-199">MutualSslNegotiated</span></span>|<span data-ttu-id="78cff-200">X509</span><span class="sxs-lookup"><span data-stu-id="78cff-200">X509</span></span>|<span data-ttu-id="78cff-201">X509, TLS-Nego</span><span class="sxs-lookup"><span data-stu-id="78cff-201">X509, TLS-Nego</span></span>|<span data-ttu-id="78cff-202">Message</span><span class="sxs-lookup"><span data-stu-id="78cff-202">Message</span></span>|  
|<span data-ttu-id="78cff-203">IssuedTokenForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="78cff-203">IssuedTokenForSslNegotiated</span></span>|<span data-ttu-id="78cff-204">Federado</span><span class="sxs-lookup"><span data-stu-id="78cff-204">Federated</span></span>|<span data-ttu-id="78cff-205">X509, TLS-Nego</span><span class="sxs-lookup"><span data-stu-id="78cff-205">X509, TLS-Nego</span></span>|<span data-ttu-id="78cff-206">Message</span><span class="sxs-lookup"><span data-stu-id="78cff-206">Message</span></span>|  
  
 <span data-ttu-id="78cff-207">Los extremos que usan tales modos de autenticación pueden expresar sus requisitos de seguridad mediante WS-SecurityPolicy (WS-SP).</span><span class="sxs-lookup"><span data-stu-id="78cff-207">Endpoints using such authentication modes can express their security requirements using WS-SecurityPolicy (WS-SP).</span></span> <span data-ttu-id="78cff-208">Este documento describe la estructura de mensajes de infraestructura y encabezado de seguridad para cada modo de autenticación y proporciona ejemplos de directivas y mensajes.</span><span class="sxs-lookup"><span data-stu-id="78cff-208">This document describes the structure of security header and infrastructure messages for each authentication mode and provides examples of policies and messages.</span></span>  
  
 <span data-ttu-id="78cff-209">WCF aprovecha WS-SecureConversation para proporcionar compatibilidad con sesiones seguras para proteger los intercambios de varios mensajes entre aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="78cff-209">WCF leverages WS-SecureConversation to provide secure sessions support to protect multi-message exchanges between applications.</span></span>  <span data-ttu-id="78cff-210">Vea "Sesiones seguras" más abajo para obtener detalles de implementación.</span><span class="sxs-lookup"><span data-stu-id="78cff-210">See "Secure Sessions" below for implementation details.</span></span>  
  
 <span data-ttu-id="78cff-211">Además de los modos de autenticación, WCF proporciona la configuración para controlar los mecanismos de protección comunes que se aplican a la mayoría de los modos de autenticación basados en seguridad de mensajes, por ejemplo: orden de firma frente a operaciones de cifrado, conjuntos de algoritmos, derivación de claves y confirmación de firma.</span><span class="sxs-lookup"><span data-stu-id="78cff-211">In addition to authentication modes, WCF provides settings to control common protection mechanisms that apply to most message security-based authentication modes, for example: order of signature versus encryption operations, algorithm suites, key derivation, and signature confirmation.</span></span>  
  
 <span data-ttu-id="78cff-212">Los siguientes prefijos y espacios de nombres se utilizan en este documento.</span><span class="sxs-lookup"><span data-stu-id="78cff-212">The following prefixes and namespaces are used in this document.</span></span>  
  
|<span data-ttu-id="78cff-213">Prefijo</span><span class="sxs-lookup"><span data-stu-id="78cff-213">Prefix</span></span>|<span data-ttu-id="78cff-214">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="78cff-214">Namespace</span></span>|  
|------------|---------------|  
|<span data-ttu-id="78cff-215">s</span><span class="sxs-lookup"><span data-stu-id="78cff-215">s</span></span>|<http://www.w3.org/2003/05/soap-envelope/>|
|<span data-ttu-id="78cff-216">sp</span><span class="sxs-lookup"><span data-stu-id="78cff-216">sp</span></span>|<http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/>|
|<span data-ttu-id="78cff-217">a</span><span class="sxs-lookup"><span data-stu-id="78cff-217">a</span></span>|<http://www.w3.org/2005/08/addressing>|  
|<span data-ttu-id="78cff-218">wsse</span><span class="sxs-lookup"><span data-stu-id="78cff-218">wsse</span></span>|<span data-ttu-id="78cff-219">TBD – OASIS WSS 1,0 URI</span><span class="sxs-lookup"><span data-stu-id="78cff-219">TBD – OASIS WSS 1.0 URI</span></span>|  
|<span data-ttu-id="78cff-220">wsse11</span><span class="sxs-lookup"><span data-stu-id="78cff-220">wsse11</span></span>|<span data-ttu-id="78cff-221">TBD – OASIS WSS 1.1 URI</span><span class="sxs-lookup"><span data-stu-id="78cff-221">TBD – OASIS WSS 1.1 URI</span></span>|  
|<span data-ttu-id="78cff-222">wsu</span><span class="sxs-lookup"><span data-stu-id="78cff-222">wsu</span></span>|<span data-ttu-id="78cff-223">TBD – OASIS WSS 1.0 Utility URI</span><span class="sxs-lookup"><span data-stu-id="78cff-223">TBD – OASIS WSS 1.0 Utility URI</span></span>|  
|<span data-ttu-id="78cff-224">ds</span><span class="sxs-lookup"><span data-stu-id="78cff-224">ds</span></span>|<span data-ttu-id="78cff-225">TBD – W3C XMLDSig URI</span><span class="sxs-lookup"><span data-stu-id="78cff-225">TBD – W3C XMLDSig URI</span></span>|  
|<span data-ttu-id="78cff-226">wst</span><span class="sxs-lookup"><span data-stu-id="78cff-226">wst</span></span>|<span data-ttu-id="78cff-227">TBD – WS-Trust 2005/02 URI</span><span class="sxs-lookup"><span data-stu-id="78cff-227">TBD – WS-Trust 2005/02 URI</span></span>|  
|<span data-ttu-id="78cff-228">wssc</span><span class="sxs-lookup"><span data-stu-id="78cff-228">wssc</span></span>|<span data-ttu-id="78cff-229">TBD – WS-SecureConversation 2005/02 URI</span><span class="sxs-lookup"><span data-stu-id="78cff-229">TBD – WS-SecureConversation 2005/02 URI</span></span>|  
|<span data-ttu-id="78cff-230">wsaw</span><span class="sxs-lookup"><span data-stu-id="78cff-230">wsaw</span></span>|<span data-ttu-id="78cff-231">TBD - Espacio de nombres de directiva WS-Addressing</span><span class="sxs-lookup"><span data-stu-id="78cff-231">TBD - WS-Addressing policy namespace</span></span>|  
|<span data-ttu-id="78cff-232">wsp</span><span class="sxs-lookup"><span data-stu-id="78cff-232">wsp</span></span>|<http://schemas.xmlsoap.org/ws/2004/09/policy>|  
|<span data-ttu-id="78cff-233">mssp</span><span class="sxs-lookup"><span data-stu-id="78cff-233">mssp</span></span>|<http://schemas.xmlsoap.org/ws/2005/07/securitypolicy>|
  
## <a name="1-token-profiles"></a><span data-ttu-id="78cff-234">1. Perfiles de token</span><span class="sxs-lookup"><span data-stu-id="78cff-234">1. Token Profiles</span></span>  
 <span data-ttu-id="78cff-235">Las especificaciones Seguridad de Servicios web representan la credencial como tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="78cff-235">Web Services Security specifications represent credential as security tokens.</span></span> <span data-ttu-id="78cff-236">WCF admite los siguientes tipos de token:</span><span class="sxs-lookup"><span data-stu-id="78cff-236">WCF supports the following token types:</span></span>  
  
### <a name="11-usernametoken"></a><span data-ttu-id="78cff-237">1.1 UsernameToken</span><span class="sxs-lookup"><span data-stu-id="78cff-237">1.1 UsernameToken</span></span>  
 <span data-ttu-id="78cff-238">WCF sigue los perfiles UsernameToken10 y UsernameToken11 con las siguientes restricciones:</span><span class="sxs-lookup"><span data-stu-id="78cff-238">WCF follows UsernameToken10 and UsernameToken11 profiles with the following constraints:</span></span>  
  
 <span data-ttu-id="78cff-239">El atributo R1101 PasswordType en el elemento UsernameToken\Password no se debe omitir ni debe tener el valor #PasswordText (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="78cff-239">R1101 PasswordType attribute on UsernameToken\Password element MUST be either omitted or have value #PasswordText (default).</span></span>  
  
 <span data-ttu-id="78cff-240">Uno puede implementar el #PasswordDigest mediante extensibilidad.</span><span class="sxs-lookup"><span data-stu-id="78cff-240">One can implement the #PasswordDigest using extensibility.</span></span> <span data-ttu-id="78cff-241">Se ha observado que #PasswordDigest se confunde a menudo como un mecanismo de protección de contraseña suficientemente seguro.</span><span class="sxs-lookup"><span data-stu-id="78cff-241">It has been observed that #PasswordDigest was often mistaken to be a secure enough password protection mechanism.</span></span> <span data-ttu-id="78cff-242">Pero #PasswordDigest no puede actuar como un sustituto del cifrado del UsernameToken.</span><span class="sxs-lookup"><span data-stu-id="78cff-242">But #PasswordDigest cannot serve as a substitute for encryption of the UsernameToken.</span></span> <span data-ttu-id="78cff-243">El objetivo principal de #PasswordDigest es la protección frente a ataques mediante repetición.</span><span class="sxs-lookup"><span data-stu-id="78cff-243">The primary goal of #PasswordDigest is protection against replay attacks.</span></span> <span data-ttu-id="78cff-244">En los modos de autenticación WCF, las amenazas de ataque de reproducción se mitigan mediante firmas de mensaje.</span><span class="sxs-lookup"><span data-stu-id="78cff-244">In WCF authentication modes, replay attack threats are mitigated by using message signatures.</span></span>  
  
 <span data-ttu-id="78cff-245">B1102 WCF nunca emite Nonce y Created subelementos de la UsernameToken.</span><span class="sxs-lookup"><span data-stu-id="78cff-245">B1102 WCF never emits Nonce and Created sub-elements of the UsernameToken.</span></span>  
  
 <span data-ttu-id="78cff-246">Estos subelementos están diseñados para ayudar a detectar las repeticiones.</span><span class="sxs-lookup"><span data-stu-id="78cff-246">These sub-elements are intended to help replay detection.</span></span> <span data-ttu-id="78cff-247">WCF usa firmas de mensaje en su lugar.</span><span class="sxs-lookup"><span data-stu-id="78cff-247">WCF uses message signatures instead.</span></span>  
  
 <span data-ttu-id="78cff-248">Perfil 1.1 de UsernameToken de seguridad de mensajes SOAP WSS OASIS (UsernameToken11) introdujo la característica de derivación de claves a partir de la contraseña.</span><span class="sxs-lookup"><span data-stu-id="78cff-248">OASIS WSS SOAP Message Security UsernameToken Profile 1.1 (UsernameToken11) introduced key derivation from password feature.</span></span>  
  
 <span data-ttu-id="78cff-249">La contraseña de UsernameToken B1103 no se debe utilizar para la derivación de claves ni, por consiguiente, para las operaciones criptográficas.</span><span class="sxs-lookup"><span data-stu-id="78cff-249">B1103 UsernameToken password MUST not be used for key derivation and therefore for cryptographic operations.</span></span>  
  
 <span data-ttu-id="78cff-250">Razón: las contraseñas generalmente están consideradas demasiado débiles como para ser utilizadas para operaciones criptográficas.</span><span class="sxs-lookup"><span data-stu-id="78cff-250">Rationale: passwords are generally considered too weak to be used for cryptographic operations.</span></span>  
  
### <a name="12-x509-token"></a><span data-ttu-id="78cff-251">1.2 Token X509</span><span class="sxs-lookup"><span data-stu-id="78cff-251">1.2 X509 Token</span></span>  
 <span data-ttu-id="78cff-252">WCF admite certificados X509v3 como tipo de credencial y sigue X509TokenProfile1.0 y X509TokenProfile1.1 con las siguientes restricciones:</span><span class="sxs-lookup"><span data-stu-id="78cff-252">WCF supports X509v3 certificates as a credential type and follows X509TokenProfile1.0 and X509TokenProfile1.1 with the following constraints:</span></span>  
  
 <span data-ttu-id="78cff-253">R1201 El atributo ValueType en el elemento BinarySecurityToken debe tener el valor #X509v3 cuando contiene un certificado X509v3.</span><span class="sxs-lookup"><span data-stu-id="78cff-253">R1201 The ValueType attribute on the BinarySecurityToken element must have value #X509v3 when it contains an X509v3 certificate.</span></span>  
  
 <span data-ttu-id="78cff-254">Los perfiles 1.0 y 1.1 de token de WSS X509 también definen #X509PKIPathv1 y #PKCS7 como tipos de valor.</span><span class="sxs-lookup"><span data-stu-id="78cff-254">WSS X509 Token Profile 1.0 and 1.1 define also #X509PKIPathv1 and #PKCS7 as value types.</span></span> <span data-ttu-id="78cff-255">WCF no admite estos tipos.</span><span class="sxs-lookup"><span data-stu-id="78cff-255">WCF does not support these types.</span></span>  
  
 <span data-ttu-id="78cff-256">R1202 Si una extensión SubjectKeyIdentifier (SKI) se encuentra en un certificado X509, se debería utilizar wsse:KeyIdentifier para las referencias externas al token, con el atributo ValueType como #X509SubjectKeyIdentifier, y su contenido el valor codificado en base64 de la extensión SKI del certificado.</span><span class="sxs-lookup"><span data-stu-id="78cff-256">R1202 If a SubjectKeyIdentifier (SKI) extension is present in an X509 certificate, wsse:KeyIdentifier should be used for external references to the token, with the ValueType attribute as #X509SubjectKeyIdentifier and its content the base64-encoded value of certificate's SKI extension.</span></span>  
  
 <span data-ttu-id="78cff-257">Las referencias SKI se implementan ampliamente y demuestran ser un tipo de referencia externa muy interoperable.</span><span class="sxs-lookup"><span data-stu-id="78cff-257">SKI references are widely implemented and proven to be a highly interoperable external reference type.</span></span>  
  
 <span data-ttu-id="78cff-258">R1203 Una referencia externa al token de seguridad X509 NO DEBERÍA utilizar ds:X509IssuerSerial.</span><span class="sxs-lookup"><span data-stu-id="78cff-258">R1203 An external Reference to X509 Security Token SHOULD NOT use ds:X509IssuerSerial.</span></span>  
  
 <span data-ttu-id="78cff-259">R1204 Si se está utilizando X509TokenProfile1.1, una referencia externa al token de seguridad X509 DEBERÍA utilizar la huella digital introducida por WS-Security 1.1.</span><span class="sxs-lookup"><span data-stu-id="78cff-259">R1204 If X509TokenProfile1.1 is in use, an external reference to X509 Security Token SHOULD use the thumbprint introduced by WS-Security 1.1.</span></span>  
  
 <span data-ttu-id="78cff-260">WCF admite X509IssuerSerial.</span><span class="sxs-lookup"><span data-stu-id="78cff-260">WCF supports X509IssuerSerial.</span></span> <span data-ttu-id="78cff-261">Sin embargo, hay problemas de interoperabilidad con X509IssuerSerial: WCF usa una cadena para comparar dos valores de X509IssuerSerial.</span><span class="sxs-lookup"><span data-stu-id="78cff-261">However There are interoperability issues with X509IssuerSerial: WCF uses a string to compare two values of X509IssuerSerial.</span></span> <span data-ttu-id="78cff-262">Por lo tanto, si uno reordena los componentes del nombre de sujeto y envía a un servicio WCF una referencia a un certificado, es posible que no se encuentre.</span><span class="sxs-lookup"><span data-stu-id="78cff-262">Therefore if one reorders components of the Subject Name and sends to an WCF service a reference to a certificate, it may not be found.</span></span>  
  
### <a name="13-kerberos-token"></a><span data-ttu-id="78cff-263">1.3 Token de Kerberos.</span><span class="sxs-lookup"><span data-stu-id="78cff-263">1.3 Kerberos Token</span></span>  
 <span data-ttu-id="78cff-264">WCF admite KerberosTokenProfile1.1 para el propósito de la autenticación de Windows con las siguientes restricciones:</span><span class="sxs-lookup"><span data-stu-id="78cff-264">WCF supports KerberosTokenProfile1.1 for the purpose of Windows authentication with the following constraints:</span></span>  
  
 <span data-ttu-id="78cff-265">R1301 Un Token de Kerberos debe llevar el valor de un AP_REQ de Kerberos v4 ajustado a GSS, tal y como se define en GSS_API y en la especificación de Kerberos, y debe tener el atributo ValueType con el valor #GSS_Kerberosv5_AP_REQ.</span><span class="sxs-lookup"><span data-stu-id="78cff-265">R1301 A Kerberos Token must carry the value of a GSS wrapped Kerberos v4 AP_REQ as defined in GSS_API and the Kerberos specification, and must have the ValueType attribute with the value #GSS_Kerberosv5_AP_REQ.</span></span>  
  
 <span data-ttu-id="78cff-266">WCF usa GSS envuelto Kerberos AP-REQ, no un AP-REQ desnudo.</span><span class="sxs-lookup"><span data-stu-id="78cff-266">WCF uses GSS wrapped Kerberos AP-REQ, not a bare AP-REQ.</span></span> <span data-ttu-id="78cff-267">Éste es un procedimiento de seguridad recomendado.</span><span class="sxs-lookup"><span data-stu-id="78cff-267">This is a security best practice.</span></span>  
  
### <a name="14-saml-v11-token"></a><span data-ttu-id="78cff-268">1.4 Token SAML v1.1</span><span class="sxs-lookup"><span data-stu-id="78cff-268">1.4 SAML v1.1 Token</span></span>  
 <span data-ttu-id="78cff-269">WCF admite los perfiles de token SAML de WSS 1.0 y 1.1 para los tokens SAML v1.1.</span><span class="sxs-lookup"><span data-stu-id="78cff-269">WCF supports WSS SAML Token profiles 1.0 and 1.1 for SAML v1.1 tokens.</span></span> <span data-ttu-id="78cff-270">Es posible implementar otras versiones de formatos de token SAML.</span><span class="sxs-lookup"><span data-stu-id="78cff-270">It is possible to implement other versions of SAML token formats.</span></span>  
  
### <a name="15-security-context-token"></a><span data-ttu-id="78cff-271">1.5 Token de contexto de seguridad</span><span class="sxs-lookup"><span data-stu-id="78cff-271">1.5 Security Context Token</span></span>  
 <span data-ttu-id="78cff-272">WCF admite el token de contexto de seguridad (SCT) introducido en WS-SecureConversation.</span><span class="sxs-lookup"><span data-stu-id="78cff-272">WCF supports the Security Context Token (SCT) introduced in WS-SecureConversation.</span></span> <span data-ttu-id="78cff-273">SCT se utiliza para representar un contexto de seguridad establecido en SecureConversation así como los protocolos de negociación binarios TLS y SSPI, descritos a continuación.</span><span class="sxs-lookup"><span data-stu-id="78cff-273">SCT is used to represent a security context established in SecureConversation as well as the binary negotiation protocols TLS and SSPI, described below.</span></span>  
  
## <a name="2-common-message-security-parameters"></a><span data-ttu-id="78cff-274">2. Parámetros comunes de seguridad de mensajes</span><span class="sxs-lookup"><span data-stu-id="78cff-274">2. Common Message Security Parameters</span></span>  
  
### <a name="21-timestamp"></a><span data-ttu-id="78cff-275">2.1 Marca de tiempo</span><span class="sxs-lookup"><span data-stu-id="78cff-275">2.1 TimeStamp</span></span>  
 <span data-ttu-id="78cff-276">La presencia de la marca de tiempo se controla mediante la propiedad <xref:System.ServiceModel.Channels.SecurityBindingElement.IncludeTimestamp%2A> de la clase <xref:System.ServiceModel.Channels.SecurityBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="78cff-276">Timestamp presence is controlled using the <xref:System.ServiceModel.Channels.SecurityBindingElement.IncludeTimestamp%2A> property of the <xref:System.ServiceModel.Channels.SecurityBindingElement> class.</span></span> <span data-ttu-id="78cff-277">WCF siempre serializa wsse:TimeStamp con wsse:Created y wsse:Expires campos.</span><span class="sxs-lookup"><span data-stu-id="78cff-277">WCF always serializes wsse:TimeStamp with wsse:Created and wsse:Expires fields.</span></span> <span data-ttu-id="78cff-278">El wsse:TimeStamp siempre se firma cuando se utilizan las firmas.</span><span class="sxs-lookup"><span data-stu-id="78cff-278">The wsse:TimeStamp is always signed when signing is used.</span></span>  
  
### <a name="22-protection-order"></a><span data-ttu-id="78cff-279">2.2 Orden de protección</span><span class="sxs-lookup"><span data-stu-id="78cff-279">2.2 Protection Order</span></span>  
 <span data-ttu-id="78cff-280">WCF admite el orden de protección de mensajes "Sign Before Encrypt" y "Encrypt Before Sign" (directiva de seguridad 1.1).</span><span class="sxs-lookup"><span data-stu-id="78cff-280">WCF supports the message protection order "Sign Before Encrypt" and "Encrypt Before Sign" (Security Policy 1.1).</span></span> <span data-ttu-id="78cff-281">"Sign Before Encrypt" se recomienda por diferentes motivos, entre los que se incluyen los siguientes: los mensajes protegidos mediante Encrypt Before Sign están expuestos a ataques de sustitución de firmas a menos que se use el mecanismo SignatureConfirmation de WS-Security 1.1, y una firma sobre el contenido cifrado dificulta la auditoría.</span><span class="sxs-lookup"><span data-stu-id="78cff-281">"Sign Before Encrypt" is recommended for reasons including: messages protected with Encrypt Before Sign are open to signature substitution attacks unless the WS-Security 1.1 SignatureConfirmation mechanism is used, and a signature over encrypted content makes auditing harder.</span></span>  
  
### <a name="23-signature-protection"></a><span data-ttu-id="78cff-282">2.3 Protección de firmas</span><span class="sxs-lookup"><span data-stu-id="78cff-282">2.3 Signature Protection</span></span>  
 <span data-ttu-id="78cff-283">Cuando se usa Cifrar antes de firmar, se recomienda proteger la firma para evitar los ataques por fuerza bruta para adivinar el contenido cifrado o la clave de la firma (sobre todo cuando un token personalizado se utiliza con material de clave débil).</span><span class="sxs-lookup"><span data-stu-id="78cff-283">When Encrypt Before Sign is used, it is recommended to protect the signature to prevent brute force attacks for guessing the encrypted content or the signing key (especially when a custom token is used with weak key material).</span></span>  
  
### <a name="24-algorithm-suite"></a><span data-ttu-id="78cff-284">2.4 Conjunto de algoritmos</span><span class="sxs-lookup"><span data-stu-id="78cff-284">2.4 Algorithm Suite</span></span>  
 <span data-ttu-id="78cff-285">WCF admite todos los conjuntos de algoritmos enumerados en la directiva de seguridad 1.1.</span><span class="sxs-lookup"><span data-stu-id="78cff-285">WCF supports all algorithm suites listed in Security Policy 1.1.</span></span>  
  
### <a name="25-key-derivation"></a><span data-ttu-id="78cff-286">2.5 Derivación de clave</span><span class="sxs-lookup"><span data-stu-id="78cff-286">2.5 Key Derivation</span></span>  
 <span data-ttu-id="78cff-287">WCF usa "Derivación de claves para claves simétricas" como se describe en WS-SecureConversation.</span><span class="sxs-lookup"><span data-stu-id="78cff-287">WCF uses "Key Derivation for symmetric keys" as described in WS-SecureConversation.</span></span>  
  
### <a name="26-signature-confirmation"></a><span data-ttu-id="78cff-288">2.6 Confirmación de firma</span><span class="sxs-lookup"><span data-stu-id="78cff-288">2.6 Signature Confirmation</span></span>  
 <span data-ttu-id="78cff-289">La confirmación de firma puede ser como protección frente a ataques de intermediarios para proteger el conjunto de firmas.</span><span class="sxs-lookup"><span data-stu-id="78cff-289">Signature confirmation can be as protection from middle man attacks to protect the set of signatures.</span></span>  
  
### <a name="27-security-header-layout"></a><span data-ttu-id="78cff-290">2.7 Diseño del encabezado de seguridad</span><span class="sxs-lookup"><span data-stu-id="78cff-290">2.7 Security Header Layout</span></span>  
 <span data-ttu-id="78cff-291">Cada modo de autenticación describe un cierto diseño para el encabezado de seguridad.</span><span class="sxs-lookup"><span data-stu-id="78cff-291">Each authentication mode describes a certain layout for the security header.</span></span> <span data-ttu-id="78cff-292">Los elementos dentro del encabezado de seguridad se semiordenan.</span><span class="sxs-lookup"><span data-stu-id="78cff-292">Elements within the security header are semi-ordered.</span></span> <span data-ttu-id="78cff-293">Para definir el orden de elementos secundarios del encabezado de seguridad, la directiva WS-Security define los siguientes modos de diseño del encabezado de seguridad:</span><span class="sxs-lookup"><span data-stu-id="78cff-293">To define the order of security header child elements, WS-Security Policy defines the following security header layout modes:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="78cff-294">Strict</span><span class="sxs-lookup"><span data-stu-id="78cff-294">Strict</span></span>|<span data-ttu-id="78cff-295">Los elementos se agregan al encabezado de seguridad siguiendo las reglas de diseño descritas en la sección 7.7.1 de la Directiva de seguridad, según un principio general de "declarar antes de usar".</span><span class="sxs-lookup"><span data-stu-id="78cff-295">Items are added to the security header following the numbered layout rules described in Security Policy section 7.7.1 according to a general principle of "declare before use".</span></span>|  
|<span data-ttu-id="78cff-296">Lax</span><span class="sxs-lookup"><span data-stu-id="78cff-296">Lax</span></span>|<span data-ttu-id="78cff-297">Los elementos se agregan al encabezado de seguridad en cualquier orden que cumpla con la seguridad de mensajes WSS: SOAP.</span><span class="sxs-lookup"><span data-stu-id="78cff-297">Items are added to the security header in any order that conforms to WSS: SOAP Message Security.</span></span>|  
|<span data-ttu-id="78cff-298">LaxTimestampFirst</span><span class="sxs-lookup"><span data-stu-id="78cff-298">LaxTimestampFirst</span></span>|<span data-ttu-id="78cff-299">Igual que Lax, solo que el primer elemento en el encabezado de seguridad debe ser wsse:Timestamp</span><span class="sxs-lookup"><span data-stu-id="78cff-299">Same as Lax except that the first item in the security header must be a wsse:Timestamp</span></span>|  
|<span data-ttu-id="78cff-300">LaxTimestampLast</span><span class="sxs-lookup"><span data-stu-id="78cff-300">LaxTimestampLast</span></span>|<span data-ttu-id="78cff-301">Igual que lax, solo que el último elemento en el encabezado de seguridad debe ser wsse:Timestamp</span><span class="sxs-lookup"><span data-stu-id="78cff-301">Same as lax except that the last item in the security header must be a wsse:Timestamp</span></span>|  
  
 <span data-ttu-id="78cff-302">WCF admite los cuatro modos para el diseño de encabezado de seguridad.</span><span class="sxs-lookup"><span data-stu-id="78cff-302">WCF supports all four modes for security header layout.</span></span> <span data-ttu-id="78cff-303">La estructura de encabezado de Seguridad y los ejemplos de mensajes para los modos de autenticación siguen el modo "Strict" (estricto).</span><span class="sxs-lookup"><span data-stu-id="78cff-303">Security header structure and message examples for authentication modes below follow the "Strict" mode.</span></span>  
  
## <a name="2-common-message-security-parameters"></a><span data-ttu-id="78cff-304">2. Parámetros comunes de seguridad de mensajes</span><span class="sxs-lookup"><span data-stu-id="78cff-304">2. Common Message Security Parameters</span></span>  
 <span data-ttu-id="78cff-305">En esta sección se proporcionan ejemplos de directivas para cada modo de autenticación junto con ejemplos que muestran la estructura de encabezado de seguridad en mensajes intercambiados por cliente y servicio.</span><span class="sxs-lookup"><span data-stu-id="78cff-305">This section provides example policies for each authentication mode along with examples showing security header structure in messages exchanged by client and service.</span></span>  
  
### <a name="61-transport-protection"></a><span data-ttu-id="78cff-306">6.1 Protección de transporte</span><span class="sxs-lookup"><span data-stu-id="78cff-306">6.1 Transport Protection</span></span>  
 <span data-ttu-id="78cff-307">WCF proporciona cinco modos de autenticación que usan transporte seguro para proteger los mensajes; UserNameOverTransport, CertificateOverTransport, KerberosOverTransport, IssuedTokenOverTransport y SspiNegotiatedOverTransport.</span><span class="sxs-lookup"><span data-stu-id="78cff-307">WCF provides five authentication modes that use secure transport to protect messages; UserNameOverTransport, CertificateOverTransport, KerberosOverTransport, IssuedTokenOverTransport and SspiNegotiatedOverTransport.</span></span>  
  
 <span data-ttu-id="78cff-308">Estos modos de autenticación se construyen utilizando el enlace de transportes descrito en SecurityPolicy.</span><span class="sxs-lookup"><span data-stu-id="78cff-308">These authentication modes are constructed using the transport binding described in SecurityPolicy.</span></span> <span data-ttu-id="78cff-309">Para el modo de autenticación de UserNameOverTransport, UsernameToken es un token auxiliar firmado.</span><span class="sxs-lookup"><span data-stu-id="78cff-309">For the UserNameOverTransport authentication mode the UsernameToken is a signed supporting token.</span></span> <span data-ttu-id="78cff-310">Para los otros modos de autenticación el token aparece como un token de endoso firmado.</span><span class="sxs-lookup"><span data-stu-id="78cff-310">For the other authentication modes the token appears as a signed endorsing token.</span></span> <span data-ttu-id="78cff-311">Los apéndices C.1.2 y C.1.3 de SecurityPolicy describen en detalle el diseño del encabezado de seguridad.</span><span class="sxs-lookup"><span data-stu-id="78cff-311">Appendix C.1.2 and C.1.3 of SecurityPolicy describe the security header layout in detail.</span></span> <span data-ttu-id="78cff-312">Los siguientes encabezados de seguridad del ejemplo muestran el diseño estricto para un modo de autenticación determinado.</span><span class="sxs-lookup"><span data-stu-id="78cff-312">The following example security headers show the Strict layout for a given authentication mode.</span></span>  
  
 <span data-ttu-id="78cff-313">El valor de propiedad “Derived Keys” para los tokens en todos los casos es "falsa."</span><span class="sxs-lookup"><span data-stu-id="78cff-313">The value of the "Derived Keys" property for the tokens in all cases is "false".</span></span>  
  
 <span data-ttu-id="78cff-314">Los valores de las diversas propiedades del enlace de transporte son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="78cff-314">The values of the various properties of the transport binding are as follows:</span></span>  
  
 <span data-ttu-id="78cff-315">Marca de tiempo: true</span><span class="sxs-lookup"><span data-stu-id="78cff-315">Timestamp: true</span></span>  
  
 <span data-ttu-id="78cff-316">Diseño de encabezado de seguridad: Strict</span><span class="sxs-lookup"><span data-stu-id="78cff-316">Security Header Layout: Strict</span></span>  
  
 <span data-ttu-id="78cff-317">Conjunto de algoritmos: Basic256</span><span class="sxs-lookup"><span data-stu-id="78cff-317">Algorithm Suite: Basic256</span></span>  
  
#### <a name="611-usernameovertransport"></a><span data-ttu-id="78cff-318">6.1.1 UsernameOverTransport</span><span class="sxs-lookup"><span data-stu-id="78cff-318">6.1.1 UsernameOverTransport</span></span>  
 <span data-ttu-id="78cff-319">Con este modo de autenticación, el cliente se autentica con un token de nombre de usuario que aparece en la capa de SOAP como un token auxiliar firmado que siempre se envía desde el iniciador al destinatario.</span><span class="sxs-lookup"><span data-stu-id="78cff-319">With this authentication mode, the client authenticates with a Username Token which appears at the SOAP layer as a signed supporting token that is always sent from the initiator to the recipient.</span></span> <span data-ttu-id="78cff-320">La autenticación del servicio se realiza mediante un certificado X.509 en el nivel de transporte.</span><span class="sxs-lookup"><span data-stu-id="78cff-320">The service is authenticated using an X.509 certificate at the transport layer.</span></span> <span data-ttu-id="78cff-321">El enlace utilizado es un enlace de transporte.</span><span class="sxs-lookup"><span data-stu-id="78cff-321">The binding used is a transport binding.</span></span>  
  
 <span data-ttu-id="78cff-322">Directiva</span><span class="sxs-lookup"><span data-stu-id="78cff-322">Policy</span></span>  
  
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
  
 <span data-ttu-id="78cff-323">Diseño del encabezado de seguridad</span><span class="sxs-lookup"><span data-stu-id="78cff-323">Security Header Layout</span></span>  
  
 <span data-ttu-id="78cff-324">Solicitud</span><span class="sxs-lookup"><span data-stu-id="78cff-324">Request</span></span>  
  
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
  
 <span data-ttu-id="78cff-325">Response</span><span class="sxs-lookup"><span data-stu-id="78cff-325">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
</wsse:Security>  
```  
  
#### <a name="612-certificateovertransport"></a><span data-ttu-id="78cff-326">6.1.2 CertificateOverTransport</span><span class="sxs-lookup"><span data-stu-id="78cff-326">6.1.2 CertificateOverTransport</span></span>  
 <span data-ttu-id="78cff-327">Con este modo de autenticación el cliente se autentica utilizando un certificado X.509 que aparece en la capa de SOAP como un token auxiliar de aprobación que siempre se envía desde el iniciador al destinatario.</span><span class="sxs-lookup"><span data-stu-id="78cff-327">With this authentication mode the client authenticates using an X.509 certificate which appears at the SOAP layer as an endorsing supporting token that is always sent from the initiator to the recipient.</span></span> <span data-ttu-id="78cff-328">La autenticación del servicio se realiza mediante un certificado X.509 en el nivel de transporte.</span><span class="sxs-lookup"><span data-stu-id="78cff-328">The service is authenticated using an X.509 certificate at the transport layer.</span></span> <span data-ttu-id="78cff-329">El enlace utilizado es un enlace de transporte.</span><span class="sxs-lookup"><span data-stu-id="78cff-329">The binding used is a transport binding.</span></span>  
  
 <span data-ttu-id="78cff-330">Directiva</span><span class="sxs-lookup"><span data-stu-id="78cff-330">Policy</span></span>  
  
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
  
 <span data-ttu-id="78cff-331">Diseño del encabezado de seguridad</span><span class="sxs-lookup"><span data-stu-id="78cff-331">Security Header Layout</span></span>  
  
 <span data-ttu-id="78cff-332">Solicitud</span><span class="sxs-lookup"><span data-stu-id="78cff-332">Request</span></span>  
  
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
  
 <span data-ttu-id="78cff-333">Response</span><span class="sxs-lookup"><span data-stu-id="78cff-333">Response</span></span>  
  
```xml  
<o:Security>  
  <u:Timestamp u:Id="_0">  
  ...  
  </u:Timestamp>  
</o:Security>  
```  
  
#### <a name="613-issuedtokenovertransport"></a><span data-ttu-id="78cff-334">6.1.3 IssuedTokenOverTransport</span><span class="sxs-lookup"><span data-stu-id="78cff-334">6.1.3 IssuedTokenOverTransport</span></span>  
 <span data-ttu-id="78cff-335">Con este modo de autenticación, el cliente no se autentica al servicio como tal; sino que, en su lugar, presenta un token emitido por un servicio de token de seguridad (STS) y demuestra que conoce una clave compartida.</span><span class="sxs-lookup"><span data-stu-id="78cff-335">With this authentication mode the client does not authenticate to the service, as such, but rather presents a token issued by a Security Token Service (STS) and proves knowledge of a shared key.</span></span> <span data-ttu-id="78cff-336">El token emitido aparece en la capa de SOAP como un token auxiliar de aprobación que siempre se envía desde el iniciador al destinatario.</span><span class="sxs-lookup"><span data-stu-id="78cff-336">The issued token appears at the SOAP layer as an endorsing supporting token that is always sent from the initiator to the recipient.</span></span> <span data-ttu-id="78cff-337">La autenticación del servicio se realiza mediante un certificado X.509 en el nivel de transporte.</span><span class="sxs-lookup"><span data-stu-id="78cff-337">The service is authenticated using an X.509 certificate at the transport layer.</span></span> <span data-ttu-id="78cff-338">El enlace es un enlace de transporte.</span><span class="sxs-lookup"><span data-stu-id="78cff-338">The binding is a transport binding.</span></span>  
  
 <span data-ttu-id="78cff-339">Directiva</span><span class="sxs-lookup"><span data-stu-id="78cff-339">Policy</span></span>  
  
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
  
 <span data-ttu-id="78cff-340">Diseño del encabezado de seguridad</span><span class="sxs-lookup"><span data-stu-id="78cff-340">Security Header Layout</span></span>  
  
 <span data-ttu-id="78cff-341">Solicitud</span><span class="sxs-lookup"><span data-stu-id="78cff-341">Request</span></span>  
  
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
  
 <span data-ttu-id="78cff-342">Response</span><span class="sxs-lookup"><span data-stu-id="78cff-342">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
</wsse:Security>  
```  
  
#### <a name="614-kerberosovertransport"></a><span data-ttu-id="78cff-343">6.1.4 KerberosOverTransport</span><span class="sxs-lookup"><span data-stu-id="78cff-343">6.1.4 KerberosOverTransport</span></span>  
 <span data-ttu-id="78cff-344">Con este modo de autenticación, el cliente se autentica en el servicio utilizando un tique de Kerberos.</span><span class="sxs-lookup"><span data-stu-id="78cff-344">With this authentication mode the client authenticates to the service using a Kerberos ticket.</span></span> <span data-ttu-id="78cff-345">El token de Kerberos aparece en la capa de SOAP como un token auxiliar de aprobación.</span><span class="sxs-lookup"><span data-stu-id="78cff-345">The Kerberos token appears at the SOAP layer as an endorsing supporting token.</span></span> <span data-ttu-id="78cff-346">La autenticación del servicio se realiza mediante un certificado X.509 en el nivel de transporte.</span><span class="sxs-lookup"><span data-stu-id="78cff-346">The service is authenticated using an X.509 certificate at the transport layer.</span></span> <span data-ttu-id="78cff-347">El enlace es un enlace de transporte.</span><span class="sxs-lookup"><span data-stu-id="78cff-347">The binding is a transport binding.</span></span>  
  
 <span data-ttu-id="78cff-348">Directiva</span><span class="sxs-lookup"><span data-stu-id="78cff-348">Policy</span></span>  
  
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
  
 <span data-ttu-id="78cff-349">Diseño del encabezado de seguridad</span><span class="sxs-lookup"><span data-stu-id="78cff-349">Security Header Layout</span></span>  
  
 <span data-ttu-id="78cff-350">Solicitud</span><span class="sxs-lookup"><span data-stu-id="78cff-350">Request</span></span>  
  
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
  
 <span data-ttu-id="78cff-351">Response</span><span class="sxs-lookup"><span data-stu-id="78cff-351">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
</wsse:Security>  
```  
  
#### <a name="615-sspinegotiatedovertransport"></a><span data-ttu-id="78cff-352">6.1.5 SspiNegotiatedOverTransport</span><span class="sxs-lookup"><span data-stu-id="78cff-352">6.1.5 SspiNegotiatedOverTransport</span></span>  
 <span data-ttu-id="78cff-353">Con este modo de negociación, se usa un protocolo de negociación para realizar la autenticación del cliente y del servidor.</span><span class="sxs-lookup"><span data-stu-id="78cff-353">With this mode a negotiation protocol is used to perform client and server authentication.</span></span> <span data-ttu-id="78cff-354">Se utiliza Kerberos si es posible; de lo contrario, se utiliza NTLM.</span><span class="sxs-lookup"><span data-stu-id="78cff-354">Kerberos is used if possible, otherwise NTLM.</span></span> <span data-ttu-id="78cff-355">El SCT resultante aparece en la capa de SOAP como un token auxiliar de aprobación que siempre se envía desde el iniciador al destinatario.</span><span class="sxs-lookup"><span data-stu-id="78cff-355">The resulting SCT appears at the SOAP layer as an endorsing supporting token that is always sent from initiator to recipient.</span></span> <span data-ttu-id="78cff-356">El servicio se autentica además en el nivel de transporte por un certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="78cff-356">The service is additionally authenticated at the transport layer by an X.509 certificate.</span></span> <span data-ttu-id="78cff-357">El enlace utilizado es un enlace de transporte.</span><span class="sxs-lookup"><span data-stu-id="78cff-357">The binding used is a transport binding.</span></span> <span data-ttu-id="78cff-358">"SPNEGO" (negociación) describe cómo WCF usa el protocolo de negociación binaria SSPI con WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="78cff-358">"SPNEGO" (negotiation) describes how WCF uses SSPI binary negotiation protocol with WS-Trust.</span></span> <span data-ttu-id="78cff-359">Los ejemplos de encabezados de seguridad de esta sección tienen lugar una vez se ha establecido SCT mediante el protocolo de enlace SPNEGO.</span><span class="sxs-lookup"><span data-stu-id="78cff-359">Security header examples in this section are after the SCT has been established through the SPNEGO handshake.</span></span>  
  
 <span data-ttu-id="78cff-360">Directiva</span><span class="sxs-lookup"><span data-stu-id="78cff-360">Policy</span></span>  
  
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
  
### <a name="security-header-examples"></a><span data-ttu-id="78cff-361">Ejemplos de encabezados de seguridad</span><span class="sxs-lookup"><span data-stu-id="78cff-361">Security Header Examples</span></span>  
 <span data-ttu-id="78cff-362">Una vez se establece el token de contexto de seguridad (SCT) a través del protocolo de enlace de SPNEGO mediante negociación binaria WS-Trust, los mensajes de aplicación tienen encabezados de seguridad con la estructura siguiente.</span><span class="sxs-lookup"><span data-stu-id="78cff-362">Once the Security Context Token is established through SPNEGO handshake using WS-Trust Binary Negotiation, the application messages have security headers with the following structure.</span></span>  
  
 <span data-ttu-id="78cff-363">Solicitud</span><span class="sxs-lookup"><span data-stu-id="78cff-363">Request</span></span>  
  
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
  
 <span data-ttu-id="78cff-364">Response</span><span class="sxs-lookup"><span data-stu-id="78cff-364">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
</wsse:Security>  
```  
  
### <a name="62-using-x509-certificates-for-service-authentication"></a><span data-ttu-id="78cff-365">6.2 Uso de certificados X.509 para la autenticación de servicios</span><span class="sxs-lookup"><span data-stu-id="78cff-365">6.2 Using X.509 Certificates for Service Authentication</span></span>  
 <span data-ttu-id="78cff-366">En esta sección se describen los modos de autenticación siguientes: MutualCertificate WSS1.0, Mutual CertificateDuplex, MutualCertificate WSS1.1, AnonymousForCertificate, UserNameForCertificate y IssuedTokenForCertificate.</span><span class="sxs-lookup"><span data-stu-id="78cff-366">This section describes the following authentication modes: MutualCertificate WSS1.0, Mutual CertificateDuplex, MutualCertificate WSS1.1, AnonymousForCertificate, UserNameForCertificate and IssuedTokenForCertificate.</span></span>  
  
#### <a name="621-mutualcertificate-wss10"></a><span data-ttu-id="78cff-367">6.2.1 MutualCertificate WSS1.0</span><span class="sxs-lookup"><span data-stu-id="78cff-367">6.2.1 MutualCertificate WSS1.0</span></span>  
 <span data-ttu-id="78cff-368">Con este modo de autenticación el cliente autentica mediante un certificado X.509 que aparece en la capa de SOAP como el token del iniciador.</span><span class="sxs-lookup"><span data-stu-id="78cff-368">With this authentication mode the client authenticates using an X.509 certificate which appears at the SOAP layer as the initiator token.</span></span> <span data-ttu-id="78cff-369">La autenticación del servicio también se realiza mediante un certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="78cff-369">The service is also authenticated using an X.509 certificate.</span></span>  
  
 <span data-ttu-id="78cff-370">El enlace usado es un enlace asimétrico con los valores de propiedad siguientes:</span><span class="sxs-lookup"><span data-stu-id="78cff-370">The binding used is an asymmetric binding with the following property values:</span></span>  
  
 <span data-ttu-id="78cff-371">Token del iniciador: el certificado X.509 del cliente, con modo de inclusión establecido en …/IncludeToken/AlwaysToRecipient</span><span class="sxs-lookup"><span data-stu-id="78cff-371">Initiator Token: the client’s X.509 certificate, with inclusion mode set to …/IncludeToken/AlwaysToRecipient</span></span>  
  
 <span data-ttu-id="78cff-372">Token del destinatario: el certificado X.509 del servidor, con modo de inclusión establecido en …/IncludeToken/Never</span><span class="sxs-lookup"><span data-stu-id="78cff-372">Recipient Token: Server’s X.509 Certificate, with inclusion mode is set …/IncludeToken/Never</span></span>  
  
 <span data-ttu-id="78cff-373">Protección de tokens: False</span><span class="sxs-lookup"><span data-stu-id="78cff-373">Token Protection: False</span></span>  
  
 <span data-ttu-id="78cff-374">Encabezado completo y firmas de cuerpo: True</span><span class="sxs-lookup"><span data-stu-id="78cff-374">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="78cff-375">Orden de protección: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="78cff-375">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="78cff-376">Cifrar firma: True</span><span class="sxs-lookup"><span data-stu-id="78cff-376">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="78cff-377">Directiva</span><span class="sxs-lookup"><span data-stu-id="78cff-377">Policy</span></span>  
  
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
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="78cff-378">Ejemplos de encabezado de seguridad: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="78cff-378">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="78cff-379">Solicitud</span><span class="sxs-lookup"><span data-stu-id="78cff-379">Request</span></span>  
  
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
  
 <span data-ttu-id="78cff-380">Response</span><span class="sxs-lookup"><span data-stu-id="78cff-380">Response</span></span>  
  
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
  
 <span data-ttu-id="78cff-381">Ejemplos de encabezado de seguridad: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="78cff-381">Security Header Examples: EncryptBeforeSign</span></span>  
  
 <span data-ttu-id="78cff-382">Solicitud</span><span class="sxs-lookup"><span data-stu-id="78cff-382">Request</span></span>  
  
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
  
 <span data-ttu-id="78cff-383">Response</span><span class="sxs-lookup"><span data-stu-id="78cff-383">Response</span></span>  
  
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
  
#### <a name="622-mutualcertificateduplex"></a><span data-ttu-id="78cff-384">6.2.2 MutualCertificateDuplex</span><span class="sxs-lookup"><span data-stu-id="78cff-384">6.2.2 MutualCertificateDuplex</span></span>  
 <span data-ttu-id="78cff-385">Con este modo de autenticación el cliente autentica mediante un certificado X.509 que aparece en la capa de SOAP como el token del iniciador.</span><span class="sxs-lookup"><span data-stu-id="78cff-385">With this authentication mode the client authenticates using an X.509 certificate which appears at the SOAP layer as the initiator token.</span></span> <span data-ttu-id="78cff-386">La autenticación del servicio también se realiza mediante un certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="78cff-386">The service is also authenticated using an X.509 certificate.</span></span>  
  
 <span data-ttu-id="78cff-387">El enlace usado es un enlace asimétrico con los valores de propiedad siguientes:</span><span class="sxs-lookup"><span data-stu-id="78cff-387">The binding used is an asymmetric binding with the following property values:</span></span>  
  
 <span data-ttu-id="78cff-388">Token del iniciador: certificado X509 de cliente, modo de inclusión establecido en …/IncludeToken/AlwaysToRecipient</span><span class="sxs-lookup"><span data-stu-id="78cff-388">Initiator Token: Client’s X509 Certificate, inclusion mode is set to …/IncludeToken/AlwaysToRecipient</span></span>  
  
 <span data-ttu-id="78cff-389">Token del destinatario: certificado X509 del servidor, modo de inclusión establecido en …/IncludeToken/AlwaysToInitiator</span><span class="sxs-lookup"><span data-stu-id="78cff-389">Recipient Token: Server’s X509 Certificate, inclusion mode is set to …/IncludeToken/AlwaysToInitiator</span></span>  
  
 <span data-ttu-id="78cff-390">Protección de tokens: False</span><span class="sxs-lookup"><span data-stu-id="78cff-390">Token Protection: False</span></span>  
  
 <span data-ttu-id="78cff-391">Encabezado completo y firmas de cuerpo: True</span><span class="sxs-lookup"><span data-stu-id="78cff-391">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="78cff-392">Orden de protección: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="78cff-392">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="78cff-393">Cifrar firma: True</span><span class="sxs-lookup"><span data-stu-id="78cff-393">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="78cff-394">Directiva</span><span class="sxs-lookup"><span data-stu-id="78cff-394">Policy</span></span>  
  
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
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="78cff-395">Ejemplos de encabezado de seguridad: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="78cff-395">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="78cff-396">Solicitud y respuesta</span><span class="sxs-lookup"><span data-stu-id="78cff-396">Request and Response</span></span>  
  
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
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="78cff-397">Ejemplos de encabezado de seguridad: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="78cff-397">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="78cff-398">Solicitud y respuesta</span><span class="sxs-lookup"><span data-stu-id="78cff-398">Request and Response</span></span>  
  
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
  
#### <a name="623-using-symmetricbinding-with-x509-service-authentication"></a><span data-ttu-id="78cff-399">6.2.3 Uso de SymmetricBinding con autenticación de servicio X.509</span><span class="sxs-lookup"><span data-stu-id="78cff-399">6.2.3 Using SymmetricBinding with X.509 Service Authentication</span></span>  
 <span data-ttu-id="78cff-400">"WSS10" proporcionó compatibilidad limitada para escenarios con tokens de X509.</span><span class="sxs-lookup"><span data-stu-id="78cff-400">"WSS10" provided limited support for scenarios with X509 tokens.</span></span> <span data-ttu-id="78cff-401">Por ejemplo, no hubo manera de proporcionar protección de cifrado y firma para los mensajes que solo usan tokens de X509 de servicio.</span><span class="sxs-lookup"><span data-stu-id="78cff-401">For example, there was no way to provide signature and encryption protection for messages using only service X509 token.</span></span> <span data-ttu-id="78cff-402">"WSS11" introdujo el uso de EncryptedKey como un token simétrico.</span><span class="sxs-lookup"><span data-stu-id="78cff-402">"WSS11" introduced the usage of EncryptedKey as a symmetric token.</span></span> <span data-ttu-id="78cff-403">Ahora una clave temporal cifrada para el certificado X.509 de servicio se podría utilizar para la protección de mensajes de solicitud y respuesta.</span><span class="sxs-lookup"><span data-stu-id="78cff-403">Now a temporary key encrypted for the service's X.509 certificate could be used for both request and response messages protection.</span></span> <span data-ttu-id="78cff-404">Los modos de autenticación descritos en la sección 6.4 que se encuentra abajo usan este patrón.</span><span class="sxs-lookup"><span data-stu-id="78cff-404">The authentication modes described in the section 6.4 below use this pattern.</span></span>  
  
 <span data-ttu-id="78cff-405">WS-SecurityPolicy describe este patrón utilizando SymmetricBinding con token X509 de servicio como el token de protección.</span><span class="sxs-lookup"><span data-stu-id="78cff-405">WS-SecurityPolicy describes this pattern using SymmetricBinding with Service X509 token as the protection token.</span></span>  
  
 <span data-ttu-id="78cff-406">Los modos de autenticación AnonymousForCertificate, UsernameForCertificate, MutualCertificate WSS11 e IssuedTokenForCertificate usan una instancia similar de sp:SymmetricBinding con los siguientes valores de propiedad:</span><span class="sxs-lookup"><span data-stu-id="78cff-406">Authentication modes AnonymousForCertificate, UsernameForCertificate, MutualCertificate WSS11 and IssuedTokenForCertificate all use a similar instance of sp:SymmetricBinding with the following property values:</span></span>  
  
 <span data-ttu-id="78cff-407">Token de protección: certificado X.509 de servidor, modo de inclusión establecido en .../IncludeToken/Never</span><span class="sxs-lookup"><span data-stu-id="78cff-407">Protection Token: Server’s X509 Certificate, inclusion mode is set to .../IncludeToken/Never</span></span>  
<span data-ttu-id="78cff-408">Protección de tokens: False</span><span class="sxs-lookup"><span data-stu-id="78cff-408">Token Protection: False</span></span>  
  
 <span data-ttu-id="78cff-409">Encabezado completo y firmas de cuerpo: True</span><span class="sxs-lookup"><span data-stu-id="78cff-409">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="78cff-410">Orden de protección: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="78cff-410">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="78cff-411">Cifrar firma: True</span><span class="sxs-lookup"><span data-stu-id="78cff-411">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="78cff-412">Los modos de autenticación anteriores solo difieren en los tokens auxiliares que utilizan.</span><span class="sxs-lookup"><span data-stu-id="78cff-412">The above authentication modes only differ by the supporting tokens they use.</span></span> <span data-ttu-id="78cff-413">AnonymousForCertificate no tiene ningún token auxiliar, MutualCertificate WSS 1.1 tiene el certificado X509 de cliente como un token auxiliar de aprobación, UserNameForCertificate tiene un token de nombre de usuario como un token auxiliar firmado e IssuedTokenForCertificate tiene el token emitido como un token auxiliar de aprobación.</span><span class="sxs-lookup"><span data-stu-id="78cff-413">AnonymousForCertificate does not have any supporting tokens, MutualCertificate WSS 1.1 has the client’s X509 certificate as an endorsing supporting tokens, UserNameForCertificate has a UserName Token as a signed supporting token and IssuedTokenForCertificate has the issued token as an endorsing supporting token.</span></span>  
  
 <span data-ttu-id="78cff-414">Directiva</span><span class="sxs-lookup"><span data-stu-id="78cff-414">Policy</span></span>  
  
 <span data-ttu-id="78cff-415">Enlace simétrico</span><span class="sxs-lookup"><span data-stu-id="78cff-415">Symmetric Binding</span></span>  
  
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
  
#### <a name="624-anonymousforcertificate"></a><span data-ttu-id="78cff-416">6.2.4 AnonymousForCertificate</span><span class="sxs-lookup"><span data-stu-id="78cff-416">6.2.4 AnonymousForCertificate</span></span>  
 <span data-ttu-id="78cff-417">Con este modo de autenticación, el cliente es anónimo y el servicio se autentica utilizando un certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="78cff-417">With this authentication mode the client is anonymous and the service is authenticated using an X.509 certificate.</span></span> <span data-ttu-id="78cff-418">El enlace utilizado es una instancia de enlace simétrico tal y como se describe en 6.4.2.</span><span class="sxs-lookup"><span data-stu-id="78cff-418">The binding used is an instance of symmetric binding as described in 6.4.2.</span></span>  
  
 <span data-ttu-id="78cff-419">Directiva</span><span class="sxs-lookup"><span data-stu-id="78cff-419">Policy</span></span>  
  
 <span data-ttu-id="78cff-420">Vea "Directiva" en 6.2.3 más arriba para obtener detalles sobre enlaces</span><span class="sxs-lookup"><span data-stu-id="78cff-420">See "Policy" in 6.2.3 above for binding details</span></span>  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="78cff-421">Ejemplos de encabezado de seguridad: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="78cff-421">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="78cff-422">Solicitud</span><span class="sxs-lookup"><span data-stu-id="78cff-422">Request</span></span>  
  
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
  
 <span data-ttu-id="78cff-423">Response</span><span class="sxs-lookup"><span data-stu-id="78cff-423">Response</span></span>  
  
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
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="78cff-424">Ejemplos de encabezado de seguridad: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="78cff-424">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="78cff-425">Solicitud</span><span class="sxs-lookup"><span data-stu-id="78cff-425">Request</span></span>  
  
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
  
 <span data-ttu-id="78cff-426">Response</span><span class="sxs-lookup"><span data-stu-id="78cff-426">Response</span></span>  
  
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
  
#### <a name="625-usernameforcertificate"></a><span data-ttu-id="78cff-427">6.2.5 UserNameForCertificate</span><span class="sxs-lookup"><span data-stu-id="78cff-427">6.2.5 UserNameForCertificate</span></span>  
 <span data-ttu-id="78cff-428">Con este modo de autenticación el cliente se autentica en el servicio utilizando un token de nombre de usuario que aparece en la capa SOAP como un token auxiliar firmado.</span><span class="sxs-lookup"><span data-stu-id="78cff-428">With this authentication mode the client authenticates to the service using a Username Token which appears at the SOAP layer as a signed supporting token.</span></span> <span data-ttu-id="78cff-429">El servicio autentica al cliente utilizando un certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="78cff-429">The service authenticates to the client using an X.509 certificate.</span></span> <span data-ttu-id="78cff-430">El enlace utilizado es un enlace simétrico donde el token de protección es una clave generada por el cliente, cifrada con la clave pública del servicio.</span><span class="sxs-lookup"><span data-stu-id="78cff-430">The binding used is a symmetric binding with the protection token being a key generated by the client, encrypted with the public key of the service.</span></span>  
  
 <span data-ttu-id="78cff-431">Directiva</span><span class="sxs-lookup"><span data-stu-id="78cff-431">Policy</span></span>  
  
 <span data-ttu-id="78cff-432">Vea "Directiva" en 6.2.3 más arriba para obtener detalles sobre enlaces</span><span class="sxs-lookup"><span data-stu-id="78cff-432">See "Policy" in 6.2.3 above for binding details</span></span>  
  
 <span data-ttu-id="78cff-433">Token auxiliar firmado</span><span class="sxs-lookup"><span data-stu-id="78cff-433">Signed Supporting Token</span></span>  
  
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
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="78cff-434">Ejemplos de encabezado de seguridad: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="78cff-434">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="78cff-435">Solicitud</span><span class="sxs-lookup"><span data-stu-id="78cff-435">Request</span></span>  
  
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
  
 <span data-ttu-id="78cff-436">Response</span><span class="sxs-lookup"><span data-stu-id="78cff-436">Response</span></span>  
  
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
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="78cff-437">Ejemplos de encabezado de seguridad: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="78cff-437">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="78cff-438">Solicitud</span><span class="sxs-lookup"><span data-stu-id="78cff-438">Request</span></span>  
  
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
  
 <span data-ttu-id="78cff-439">Response</span><span class="sxs-lookup"><span data-stu-id="78cff-439">Response</span></span>  
  
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
  
#### <a name="626-mutualcertificate-wss-11"></a><span data-ttu-id="78cff-440">6.2.6 MutualCertificate (WSS 1.1)</span><span class="sxs-lookup"><span data-stu-id="78cff-440">6.2.6 MutualCertificate (WSS 1.1)</span></span>  
 <span data-ttu-id="78cff-441">Con este modo de autenticación el cliente se autentica mediante un certificado X.509 que aparece en la capa SOAP como el token auxiliar de aprobación.</span><span class="sxs-lookup"><span data-stu-id="78cff-441">With this authentication mode the client authenticates using an X.509 certificate which appears at the SOAP layer as an endorsing supporting token.</span></span> <span data-ttu-id="78cff-442">La autenticación del servicio también se realiza mediante un certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="78cff-442">The service is also authenticated using an X.509 certificate.</span></span> <span data-ttu-id="78cff-443">El enlace utilizado es un enlace simétrico donde el token de protección es una clave generada por el cliente, cifrada con la clave pública del servicio.</span><span class="sxs-lookup"><span data-stu-id="78cff-443">The binding used is a symmetric binding with the protection token being a key generated by the client, encrypted with the public key of the service.</span></span>  
  
 <span data-ttu-id="78cff-444">Directiva</span><span class="sxs-lookup"><span data-stu-id="78cff-444">Policy</span></span>  
  
 <span data-ttu-id="78cff-445">Vea Directiva en 6.2.3 para obtener detalles sobre enlaces</span><span class="sxs-lookup"><span data-stu-id="78cff-445">See Policy in 6.2.3 for binding details</span></span>  
  
 <span data-ttu-id="78cff-446">Aprobar token auxiliar</span><span class="sxs-lookup"><span data-stu-id="78cff-446">Endorsing Supporting Token</span></span>  
  
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
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="78cff-447">Ejemplos de encabezado de seguridad: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="78cff-447">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="78cff-448">Solicitud</span><span class="sxs-lookup"><span data-stu-id="78cff-448">Request</span></span>  
  
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
  
 <span data-ttu-id="78cff-449">Response</span><span class="sxs-lookup"><span data-stu-id="78cff-449">Response</span></span>  
  
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
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="78cff-450">Ejemplos de encabezado de seguridad: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="78cff-450">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="78cff-451">Solicitud</span><span class="sxs-lookup"><span data-stu-id="78cff-451">Request</span></span>  
  
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
  
 <span data-ttu-id="78cff-452">Response</span><span class="sxs-lookup"><span data-stu-id="78cff-452">Response</span></span>  
  
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
  
#### <a name="627-issuedtokenforcertificate"></a><span data-ttu-id="78cff-453">6.2.7 IssuedTokenForCertificate</span><span class="sxs-lookup"><span data-stu-id="78cff-453">6.2.7 IssuedTokenForCertificate</span></span>  
 <span data-ttu-id="78cff-454">Con este modo de autenticación, el cliente no se autentica al servicio como tal; sino que, en su lugar, presenta un token emitido por un STS y demuestra que conoce una clave compartida.</span><span class="sxs-lookup"><span data-stu-id="78cff-454">With this authentication mode the client does not authenticate to the service, as such, but instead presents a token issued by a STS and proves knowledge of a shared key.</span></span> <span data-ttu-id="78cff-455">El token emitido aparece en la capa de SOAP como un token auxiliar de aprobación.</span><span class="sxs-lookup"><span data-stu-id="78cff-455">The issued token appears at the SOAP layer as an endorsing supporting token.</span></span> <span data-ttu-id="78cff-456">El servicio autentica al cliente utilizando un certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="78cff-456">The service authenticates to the client using an X.509 certificate.</span></span> <span data-ttu-id="78cff-457">El enlace utilizado es un enlace simétrico donde el token de protección es una clave generada por el cliente, cifrada con la clave pública del servicio.</span><span class="sxs-lookup"><span data-stu-id="78cff-457">The binding used is a symmetric binding with the protection token being a key generated by the client, encrypted with the public key of the service.</span></span>  
  
 <span data-ttu-id="78cff-458">Directiva</span><span class="sxs-lookup"><span data-stu-id="78cff-458">Policy</span></span>  
  
 <span data-ttu-id="78cff-459">Vea Directiva en 6.2.3 más arriba para obtener detalles sobre enlaces</span><span class="sxs-lookup"><span data-stu-id="78cff-459">See Policy in 6.2.3 above for binding details</span></span>  
  
 <span data-ttu-id="78cff-460">Aprobar token auxiliar</span><span class="sxs-lookup"><span data-stu-id="78cff-460">Endorsing Supporting Token</span></span>  
  
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
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="78cff-461">Ejemplos de encabezado de seguridad: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="78cff-461">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="78cff-462">Solicitud</span><span class="sxs-lookup"><span data-stu-id="78cff-462">Request</span></span>  
  
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
  
 <span data-ttu-id="78cff-463">Response</span><span class="sxs-lookup"><span data-stu-id="78cff-463">Response</span></span>  
  
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
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="78cff-464">Ejemplos de encabezado de seguridad: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="78cff-464">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="78cff-465">Solicitud</span><span class="sxs-lookup"><span data-stu-id="78cff-465">Request</span></span>  
  
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
  
 <span data-ttu-id="78cff-466">Response</span><span class="sxs-lookup"><span data-stu-id="78cff-466">Response</span></span>  
  
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
  
## <a name="63-kerberos"></a><span data-ttu-id="78cff-467">6.3 Kerberos</span><span class="sxs-lookup"><span data-stu-id="78cff-467">6.3 Kerberos</span></span>  
 <span data-ttu-id="78cff-468">Con este modo de autenticación, el cliente se autentica en el servicio utilizando un tique de Kerberos.</span><span class="sxs-lookup"><span data-stu-id="78cff-468">With this authentication mode the client authenticates to the service using a Kerberos ticket.</span></span> <span data-ttu-id="78cff-469">Ese mismo vale también proporciona autenticación del servidor.</span><span class="sxs-lookup"><span data-stu-id="78cff-469">That same ticket also provides server authentication.</span></span> <span data-ttu-id="78cff-470">El enlace utilizado es un enlace simétrico con las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="78cff-470">The binding used is a symmetric binding with the following properties;</span></span>  
  
 <span data-ttu-id="78cff-471">Token de protección: vale de Kerberos, modo de inclusión establecido en .../IncludeToken/Once</span><span class="sxs-lookup"><span data-stu-id="78cff-471">Protection Token: Kerberos Ticket, inclusion mode is set to .../IncludeToken/Once</span></span>  
<span data-ttu-id="78cff-472">Protección de tokens: False</span><span class="sxs-lookup"><span data-stu-id="78cff-472">Token Protection: False</span></span>  
  
 <span data-ttu-id="78cff-473">Encabezado completo y firmas de cuerpo: True</span><span class="sxs-lookup"><span data-stu-id="78cff-473">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="78cff-474">Orden de protección: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="78cff-474">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="78cff-475">Cifrar firma: True</span><span class="sxs-lookup"><span data-stu-id="78cff-475">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="78cff-476">Directiva</span><span class="sxs-lookup"><span data-stu-id="78cff-476">Policy</span></span>  
  
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
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="78cff-477">Ejemplos de encabezado de seguridad: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="78cff-477">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="78cff-478">Solicitud</span><span class="sxs-lookup"><span data-stu-id="78cff-478">Request</span></span>  
  
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
  
 <span data-ttu-id="78cff-479">Response</span><span class="sxs-lookup"><span data-stu-id="78cff-479">Response</span></span>  
  
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
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="78cff-480">Ejemplos de encabezado de seguridad: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="78cff-480">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="78cff-481">Solicitud</span><span class="sxs-lookup"><span data-stu-id="78cff-481">Request</span></span>  
  
```xml  
<wsse:Security>  
TBD  
</wsse:Security>  
```  
  
 <span data-ttu-id="78cff-482">Response</span><span class="sxs-lookup"><span data-stu-id="78cff-482">Response</span></span>  
  
```xml  
<wsse:Security>  
TBD  
</wsse:Security>  
```  
  
#### <a name="64-issuedtoken"></a><span data-ttu-id="78cff-483">6.4 IssuedToken</span><span class="sxs-lookup"><span data-stu-id="78cff-483">6.4 IssuedToken</span></span>  
 <span data-ttu-id="78cff-484">Con este modo de autenticación, el cliente no se autentica en el servicio como tal; sino que, en su lugar, presenta un token emitido por un STS y demuestra que conoce una clave compartida.</span><span class="sxs-lookup"><span data-stu-id="78cff-484">With this authentication mode the client does not authenticate to the service, as such, rather the client presents a token issued by an STS and proves knowledge of a shared key.</span></span> <span data-ttu-id="78cff-485">El servicio no se autentica al cliente como tal, sino que, en su lugar, el STS cifra la clave compartida como parte del token emitido, de manera que solo el servicio puede descifrar la clave.</span><span class="sxs-lookup"><span data-stu-id="78cff-485">The service is not authenticated to the client, as such, instead the STS encrypts the shared key as part of the issued token such that only the service can decrypt the key.</span></span> <span data-ttu-id="78cff-486">El enlace utilizado es un enlace simétrico con las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="78cff-486">The binding used is as symmetric binding with the following properties;</span></span>  
  
 <span data-ttu-id="78cff-487">Token de protección: token emitido, modo de inclusión establecido en .../IncludeToken/AlwaysToRecipient</span><span class="sxs-lookup"><span data-stu-id="78cff-487">Protection Token: Issued Token, inclusion mode is set to .../IncludeToken/AlwaysToRecipient</span></span>  
<span data-ttu-id="78cff-488">Protección de tokens: False</span><span class="sxs-lookup"><span data-stu-id="78cff-488">Token Protection: False</span></span>  
  
 <span data-ttu-id="78cff-489">Encabezado completo y firmas de cuerpo: True</span><span class="sxs-lookup"><span data-stu-id="78cff-489">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="78cff-490">Orden de protección: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="78cff-490">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="78cff-491">Cifrar firma: True</span><span class="sxs-lookup"><span data-stu-id="78cff-491">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="78cff-492">Directiva</span><span class="sxs-lookup"><span data-stu-id="78cff-492">Policy</span></span>  
  
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
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="78cff-493">Ejemplos de encabezado de seguridad: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="78cff-493">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="78cff-494">Solicitud</span><span class="sxs-lookup"><span data-stu-id="78cff-494">Request</span></span>  
  
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
  
 <span data-ttu-id="78cff-495">Response</span><span class="sxs-lookup"><span data-stu-id="78cff-495">Response</span></span>  
  
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
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="78cff-496">Ejemplos de encabezado de seguridad: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="78cff-496">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="78cff-497">Solicitud</span><span class="sxs-lookup"><span data-stu-id="78cff-497">Request</span></span>  
  
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
  
 <span data-ttu-id="78cff-498">Response</span><span class="sxs-lookup"><span data-stu-id="78cff-498">Response</span></span>  
  
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
  
### <a name="65-using-sslnegotiated-for-service-authentication"></a><span data-ttu-id="78cff-499">6.5 Uso de SslNegotiated para la autenticación de servicio</span><span class="sxs-lookup"><span data-stu-id="78cff-499">6.5 Using SslNegotiated for Service Authentication</span></span>  
 <span data-ttu-id="78cff-500">En esta sección se describe un grupo de modos de autenticación que utilizan un enlace simétrico donde el token de protección es un token de contexto de seguridad por WS-SecureConversation (WS SC), cuyo valor de clave se negocia ejecutando el protocolo TLS sobre mensajes de RST/RSTR de WS-Trust (WS-T).</span><span class="sxs-lookup"><span data-stu-id="78cff-500">This section describes a group of authentication modes that use a symmetric binding with the protection token being a Security Context Token per WS-SecureConversation (WS-SC) whose key value is negotiated by executing the TLS protocol over WS-Trust (WS-T) RST/RSTR messages.</span></span> <span data-ttu-id="78cff-501">En TLSNEGO se describen los detalles de la implementación del protocolo de enlace de TLS mediante WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="78cff-501">Details of the TLS handshake implementation using WS-Trust are described in TLSNEGO.</span></span> <span data-ttu-id="78cff-502">Aquí en los ejemplos de mensajes supondremos que SCT con un contexto de seguridad asociado ya se establece a través de un protocolo de enlace.</span><span class="sxs-lookup"><span data-stu-id="78cff-502">Here in the message examples we will assume that SCT with an associated security context is already established through a handshake.</span></span>  
  
 <span data-ttu-id="78cff-503">El enlace utilizado es un enlace simétrico con las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="78cff-503">The binding used is a symmetric binding with the following properties;</span></span>  
  
 <span data-ttu-id="78cff-504">Token de protección: SslContextToken, modo de inclusión establecido en .../IncludeToken/Never</span><span class="sxs-lookup"><span data-stu-id="78cff-504">Protection Token: SslContextToken, inclusion mode is set to .../IncludeToken/Never</span></span>  
<span data-ttu-id="78cff-505">Protección de tokens: False</span><span class="sxs-lookup"><span data-stu-id="78cff-505">Token Protection: False</span></span>  
  
 <span data-ttu-id="78cff-506">Encabezado completo y firmas de cuerpo: True</span><span class="sxs-lookup"><span data-stu-id="78cff-506">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="78cff-507">Orden de protección: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="78cff-507">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="78cff-508">Cifrar firma: True</span><span class="sxs-lookup"><span data-stu-id="78cff-508">Encrypt Signature: True</span></span>  
  
#### <a name="651-policy-for-sslnegotiated-service-authentication"></a><span data-ttu-id="78cff-509">6.5.1 Directiva para la autenticación de servicio SslNegotiated</span><span class="sxs-lookup"><span data-stu-id="78cff-509">6.5.1 Policy for SslNegotiated service authentication</span></span>  
 <span data-ttu-id="78cff-510">La directiva para todos los modos de autenticación de esta sección es similar y solo difieren en los tokens auxiliares firmados o aprobados empleados.</span><span class="sxs-lookup"><span data-stu-id="78cff-510">Policy for all authentication modes in this section are similar and differ only by specific signed supporting or endorsing tokens used.</span></span>  
  
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
  
#### <a name="652-anonymousforsslnegotiated"></a><span data-ttu-id="78cff-511">6.5.2 AnonymousForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="78cff-511">6.5.2 AnonymousForSslNegotiated</span></span>  
 <span data-ttu-id="78cff-512">Con este modo de autenticación, el cliente es anónimo y el servicio se autentica utilizando un certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="78cff-512">With this authentication mode the client is anonymous and the service is authenticated using an X.509 certificate.</span></span> <span data-ttu-id="78cff-513">El enlace utilizado es una instancia de enlace simétrico tal y como se describe en 6.5.1 más arriba.</span><span class="sxs-lookup"><span data-stu-id="78cff-513">The binding used is an instance of symmetric binding as described in 6.5.1 above.</span></span>  
  
 <span data-ttu-id="78cff-514">Directiva</span><span class="sxs-lookup"><span data-stu-id="78cff-514">Policy</span></span>  
  
 <span data-ttu-id="78cff-515">Vea Directiva en 6.5.1 más arriba para obtener detalles sobre enlaces.</span><span class="sxs-lookup"><span data-stu-id="78cff-515">See Policy in 6.5.1 above for binding details.</span></span>  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="78cff-516">Ejemplos de encabezado de seguridad: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="78cff-516">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="78cff-517">Solicitud</span><span class="sxs-lookup"><span data-stu-id="78cff-517">Request</span></span>  
  
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
  
 <span data-ttu-id="78cff-518">Response</span><span class="sxs-lookup"><span data-stu-id="78cff-518">Response</span></span>  
  
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
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="78cff-519">Ejemplos de encabezado de seguridad: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="78cff-519">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="78cff-520">Solicitud</span><span class="sxs-lookup"><span data-stu-id="78cff-520">Request</span></span>  
  
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
  
 <span data-ttu-id="78cff-521">Response</span><span class="sxs-lookup"><span data-stu-id="78cff-521">Response</span></span>  
  
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
  
#### <a name="653-usernameforsslnegotiated"></a><span data-ttu-id="78cff-522">6.5.3 UserNameForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="78cff-522">6.5.3 UserNameForSslNegotiated</span></span>  
 <span data-ttu-id="78cff-523">Con este modo de autenticación el cliente se autentica el servicio utilizando un token de nombre de usuario que aparece en la capa SOAP como un token auxiliar firmado.</span><span class="sxs-lookup"><span data-stu-id="78cff-523">With this authentication mode the client is authenticates using a Username Token which appears at the SOAP layer as a signed supporting token.</span></span> <span data-ttu-id="78cff-524">La autenticación del servicio se realiza mediante un certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="78cff-524">The service is authenticated using an X.509 certificate.</span></span> <span data-ttu-id="78cff-525">El enlace utilizado es una instancia de enlace simétrico tal y como se describe en 6.5.1.</span><span class="sxs-lookup"><span data-stu-id="78cff-525">The binding used is an instance of symmetric binding as described in 6.5.1.</span></span>  
  
 <span data-ttu-id="78cff-526">Directiva</span><span class="sxs-lookup"><span data-stu-id="78cff-526">Policy</span></span>  
  
 <span data-ttu-id="78cff-527">Vea la sección 6.5.1 anterior para obtener detalles sobre los enlaces</span><span class="sxs-lookup"><span data-stu-id="78cff-527">See section 6.5.1 above for binding details</span></span>  
  
 <span data-ttu-id="78cff-528">Token auxiliar firmado</span><span class="sxs-lookup"><span data-stu-id="78cff-528">Signed Supporting Token</span></span>  
  
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
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="78cff-529">Ejemplos de encabezado de seguridad: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="78cff-529">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="78cff-530">Solicitud</span><span class="sxs-lookup"><span data-stu-id="78cff-530">Request</span></span>  
  
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
  
 <span data-ttu-id="78cff-531">Response</span><span class="sxs-lookup"><span data-stu-id="78cff-531">Response</span></span>  
  
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
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="78cff-532">Ejemplos de encabezado de seguridad: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="78cff-532">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="78cff-533">Solicitud</span><span class="sxs-lookup"><span data-stu-id="78cff-533">Request</span></span>  
  
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
  
 <span data-ttu-id="78cff-534">Response</span><span class="sxs-lookup"><span data-stu-id="78cff-534">Response</span></span>  
  
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
  
#### <a name="654-issuedtokenforsslnegotiated"></a><span data-ttu-id="78cff-535">6.5.4 IssuedTokenForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="78cff-535">6.5.4 IssuedTokenForSslNegotiated</span></span>  
 <span data-ttu-id="78cff-536">Con este modo de autenticación, el cliente no se autentica al servicio como tal; sino que, en su lugar, presenta un token emitido por un STS y demuestra que conoce una clave compartida.</span><span class="sxs-lookup"><span data-stu-id="78cff-536">With this authentication mode the client does not authenticate to the service, as such, but instead presents a token issued by an STS and proves knowledge of a shared key.</span></span> <span data-ttu-id="78cff-537">El token emitido aparece en la capa de SOAP como un token auxiliar de aprobación.</span><span class="sxs-lookup"><span data-stu-id="78cff-537">The issued token appears at the SOAP layer as an endorsing supporting token.</span></span> <span data-ttu-id="78cff-538">La autenticación del servicio se realiza mediante un certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="78cff-538">The service is authenticated using an X.509 certificate.</span></span> <span data-ttu-id="78cff-539">El enlace utilizado es una instancia de enlace simétrico tal y como se describe en 6.5.1 más arriba.</span><span class="sxs-lookup"><span data-stu-id="78cff-539">The binding used is an instance of symmetric binding as described in 6.5.1 above.</span></span>  
  
 <span data-ttu-id="78cff-540">Directiva</span><span class="sxs-lookup"><span data-stu-id="78cff-540">Policy</span></span>  
  
 <span data-ttu-id="78cff-541">Vea la sección 6.5.1 anterior para obtener detalles sobre los enlaces</span><span class="sxs-lookup"><span data-stu-id="78cff-541">See section 6.5.1 above for binding details</span></span>  
  
 <span data-ttu-id="78cff-542">Aprobar token auxiliar</span><span class="sxs-lookup"><span data-stu-id="78cff-542">Endorsing Supporting Token</span></span>  
  
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
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="78cff-543">Ejemplos de encabezado de seguridad: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="78cff-543">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="78cff-544">Solicitud</span><span class="sxs-lookup"><span data-stu-id="78cff-544">Request</span></span>  
  
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
  
 <span data-ttu-id="78cff-545">Response</span><span class="sxs-lookup"><span data-stu-id="78cff-545">Response</span></span>  
  
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
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="78cff-546">Ejemplos de encabezado de seguridad: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="78cff-546">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="78cff-547">Solicitud</span><span class="sxs-lookup"><span data-stu-id="78cff-547">Request</span></span>  
  
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
  
 <span data-ttu-id="78cff-548">Response</span><span class="sxs-lookup"><span data-stu-id="78cff-548">Response</span></span>  
  
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
  
#### <a name="655-mutualsslnegotiated"></a><span data-ttu-id="78cff-549">6.5.5 MutualSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="78cff-549">6.5.5 MutualSslNegotiated</span></span>  
 <span data-ttu-id="78cff-550">Con este modo de autenticación, el cliente y el servicio autentican utilizando los certificados X.509.</span><span class="sxs-lookup"><span data-stu-id="78cff-550">With this authentication mode the client and the service authenticate using X.509 certificates.</span></span> <span data-ttu-id="78cff-551">El enlace utilizado es una instancia de enlace simétrico tal y como se describe en 6.5.1 más arriba.</span><span class="sxs-lookup"><span data-stu-id="78cff-551">The binding used is an instance of symmetric binding as described in 6.5.1 above.</span></span>  
  
 <span data-ttu-id="78cff-552">Directiva</span><span class="sxs-lookup"><span data-stu-id="78cff-552">Policy</span></span>  
  
 <span data-ttu-id="78cff-553">Vea la sección 6.5.1 anterior para obtener detalles sobre los enlaces</span><span class="sxs-lookup"><span data-stu-id="78cff-553">See section 6.5.1 above for binding details</span></span>  
  
 <span data-ttu-id="78cff-554">Aprobar token auxiliar</span><span class="sxs-lookup"><span data-stu-id="78cff-554">Endorsing Supporting Token</span></span>  
  
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
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="78cff-555">Ejemplos de encabezado de seguridad: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="78cff-555">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="78cff-556">Solicitud</span><span class="sxs-lookup"><span data-stu-id="78cff-556">Request</span></span>  
  
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
  
 <span data-ttu-id="78cff-557">Response</span><span class="sxs-lookup"><span data-stu-id="78cff-557">Response</span></span>  
  
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
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="78cff-558">Ejemplos de encabezado de seguridad: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="78cff-558">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="78cff-559">Solicitud</span><span class="sxs-lookup"><span data-stu-id="78cff-559">Request</span></span>  
  
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
  
 <span data-ttu-id="78cff-560">Response</span><span class="sxs-lookup"><span data-stu-id="78cff-560">Response</span></span>  
  
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
  
### <a name="66-sspinegotiated"></a><span data-ttu-id="78cff-561">6.6 SspiNegotiated</span><span class="sxs-lookup"><span data-stu-id="78cff-561">6.6 SspiNegotiated</span></span>  
 <span data-ttu-id="78cff-562">Con este modo de autenticación, se usa un protocolo de negociación para realizar la autenticación del cliente y del servidor.</span><span class="sxs-lookup"><span data-stu-id="78cff-562">With this authentication mode a negotiation protocol is used to perform client and server authentication.</span></span> <span data-ttu-id="78cff-563">Se utiliza Kerberos si es posible; de lo contrario, se utiliza NTLM.</span><span class="sxs-lookup"><span data-stu-id="78cff-563">Kerberos is used if possible, otherwise NTLM.</span></span> <span data-ttu-id="78cff-564">El enlace utilizado es un enlace simétrico con las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="78cff-564">The binding used is a symmetric binding with the following properties;</span></span>  
  
 <span data-ttu-id="78cff-565">Token de protección: SpnegoContextToken, modo de inclusión establecido en .../IncludeToken/AlwaysToRecipient</span><span class="sxs-lookup"><span data-stu-id="78cff-565">Protection Token: SpnegoContextToken, inclusion mode is set to .../IncludeToken/AlwaysToRecipient</span></span>  
<span data-ttu-id="78cff-566">Protección de tokens: False</span><span class="sxs-lookup"><span data-stu-id="78cff-566">Token Protection: False</span></span>  
  
 <span data-ttu-id="78cff-567">Encabezado completo y firmas de cuerpo: True</span><span class="sxs-lookup"><span data-stu-id="78cff-567">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="78cff-568">Orden de protección: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="78cff-568">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="78cff-569">Cifrar firma: True</span><span class="sxs-lookup"><span data-stu-id="78cff-569">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="78cff-570">Directiva</span><span class="sxs-lookup"><span data-stu-id="78cff-570">Policy</span></span>  
  
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
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="78cff-571">Ejemplos de encabezado de seguridad: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="78cff-571">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="78cff-572">Solicitud</span><span class="sxs-lookup"><span data-stu-id="78cff-572">Request</span></span>  
  
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
  
 <span data-ttu-id="78cff-573">Response</span><span class="sxs-lookup"><span data-stu-id="78cff-573">Response</span></span>  
  
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
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="78cff-574">Ejemplos de encabezado de seguridad: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="78cff-574">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="78cff-575">Solicitud</span><span class="sxs-lookup"><span data-stu-id="78cff-575">Request</span></span>  
  
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
  
 <span data-ttu-id="78cff-576">Response</span><span class="sxs-lookup"><span data-stu-id="78cff-576">Response</span></span>  
  
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
  
### <a name="67-secureconversation"></a><span data-ttu-id="78cff-577">6.7 SecureConversation</span><span class="sxs-lookup"><span data-stu-id="78cff-577">6.7 SecureConversation</span></span>  
 <span data-ttu-id="78cff-578">El enlace utilizado es un enlace simétrico donde el token de protección es un SCT por WS-SecureConversation (WS SC).</span><span class="sxs-lookup"><span data-stu-id="78cff-578">The binding used is a symmetric binding with the protection token being a SCT per WS-SecureConversation (WS-SC).</span></span> <span data-ttu-id="78cff-579">El SCT se negocia mediante WS-Trust (WS-Trust) o WS-SecureConversation (WS-SC) según un enlace anidado, que es en sí mismo un enlace simétrico que usa un protocolo de negociación.</span><span class="sxs-lookup"><span data-stu-id="78cff-579">The SCT is negotiated using WS-Trust (WS-Trust) or WS-SecureConversation (WS-SC) according to a nested binding, which is itself a symmetric binding that uses a negotiation protocol.</span></span> <span data-ttu-id="78cff-580">El protocolo de negociación utilizará Kerberos para realizar la autenticación de cliente y servidor si es posible.</span><span class="sxs-lookup"><span data-stu-id="78cff-580">The negotiation protocol will use Kerberos to perform client and server authentication if possible.</span></span> <span data-ttu-id="78cff-581">Si no se puede utilizar Kerberos, se volverá a NTLM.</span><span class="sxs-lookup"><span data-stu-id="78cff-581">If Kerberos cannot be used, it will fall back to NTLM.</span></span>  
  
 <span data-ttu-id="78cff-582">Directiva</span><span class="sxs-lookup"><span data-stu-id="78cff-582">Policy</span></span>  
  
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
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="78cff-583">Ejemplos de encabezado de seguridad: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="78cff-583">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="78cff-584">Solicitud</span><span class="sxs-lookup"><span data-stu-id="78cff-584">Request</span></span>  
  
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
  
 <span data-ttu-id="78cff-585">Response</span><span class="sxs-lookup"><span data-stu-id="78cff-585">Response</span></span>  
  
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
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="78cff-586">Ejemplos de encabezado de seguridad: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="78cff-586">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="78cff-587">Solicitud</span><span class="sxs-lookup"><span data-stu-id="78cff-587">Request</span></span>  
  
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
  
 <span data-ttu-id="78cff-588">Response</span><span class="sxs-lookup"><span data-stu-id="78cff-588">Response</span></span>  
  
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
