---
title: Protocolos de transacción
ms.date: 03/30/2017
ms.assetid: 2820b0ec-2f32-430c-b299-1f0e95e1f2dc
ms.openlocfilehash: 32c5da24eb7b23145d79c33a9ca1f5e5bcc22c06
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742731"
---
# <a name="transaction-protocols"></a><span data-ttu-id="a5d25-102">Protocolos de transacción</span><span class="sxs-lookup"><span data-stu-id="a5d25-102">Transaction Protocols</span></span>
<span data-ttu-id="a5d25-103">Windows Communication Foundation (WCF) implementa los protocolos WS-Atomic Transaction y WS-Coordination.</span><span class="sxs-lookup"><span data-stu-id="a5d25-103">Windows Communication Foundation (WCF) implements WS-Atomic Transaction and WS-Coordination protocols.</span></span>  
  
|<span data-ttu-id="a5d25-104">Especificación/documento</span><span class="sxs-lookup"><span data-stu-id="a5d25-104">Specification/Document</span></span>|<span data-ttu-id="a5d25-105">Version</span><span class="sxs-lookup"><span data-stu-id="a5d25-105">Version</span></span>|<span data-ttu-id="a5d25-106">Link</span><span class="sxs-lookup"><span data-stu-id="a5d25-106">Link</span></span>|  
|-----------------------------|-------------|----------|  
|<span data-ttu-id="a5d25-107">WS-Coordination</span><span class="sxs-lookup"><span data-stu-id="a5d25-107">WS-Coordination</span></span>|<span data-ttu-id="a5d25-108">1.0</span><span class="sxs-lookup"><span data-stu-id="a5d25-108">1.0</span></span><br /><br /> <span data-ttu-id="a5d25-109">1.1</span><span class="sxs-lookup"><span data-stu-id="a5d25-109">1.1</span></span>|<http://schemas.xmlsoap.org/ws/2004/10/wscoor/><br /><br /> <https://docs.oasis-open.org/ws-tx/wscoor/2006/06>|  
|<span data-ttu-id="a5d25-110">Transacción WS-Atomic</span><span class="sxs-lookup"><span data-stu-id="a5d25-110">WS-AtomicTransaction</span></span>|<span data-ttu-id="a5d25-111">1.0</span><span class="sxs-lookup"><span data-stu-id="a5d25-111">1.0</span></span><br /><br /> <span data-ttu-id="a5d25-112">1.1</span><span class="sxs-lookup"><span data-stu-id="a5d25-112">1.1</span></span>|<http://schemas.xmlsoap.org/ws/2004/10/wsat/><br /><br /> <https://docs.oasis-open.org/ws-tx/wsat/2006/06>|  
  
 <span data-ttu-id="a5d25-113">La interoperabilidad en estas especificaciones de protocolo se requiere en dos niveles: entre las aplicaciones y entre los administradores de transacciones (véase la siguiente figura).</span><span class="sxs-lookup"><span data-stu-id="a5d25-113">Interoperability on these protocol specifications is required at two levels: between applications and between transaction managers (see the following figure).</span></span> <span data-ttu-id="a5d25-114">Las especificaciones describen en gran detalle los formatos de mensajes y el intercambio de mensajes para ambos niveles de interoperabilidad.</span><span class="sxs-lookup"><span data-stu-id="a5d25-114">Specifications describe in great detail the message formats and message exchange for both interoperability levels.</span></span> <span data-ttu-id="a5d25-115">Cierta seguridad, fiabilidad y codificaciones para el intercambio de aplicación a aplicación se aplican tal y como lo hacen para el intercambio normal de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="a5d25-115">Certain security, reliability, and encodings for application-to-application exchange apply as they do for regular application exchange.</span></span> <span data-ttu-id="a5d25-116">Sin embargo, para una interoperabilidad correcta entre los administradores de transacciones es necesario el acuerdo en el enlace determinado, porque el usuario no lo configura por regla general.</span><span class="sxs-lookup"><span data-stu-id="a5d25-116">However, successful interoperability between transaction managers requires agreement on the particular binding, because it is usually not configured by the user.</span></span>  
  
 <span data-ttu-id="a5d25-117">Este tema describe una composición de la especificación de transacción WS-Atomic (WS-AT) con seguridad y describe el enlace seguro utilizado para la comunicación entre administradores de transacciones.</span><span class="sxs-lookup"><span data-stu-id="a5d25-117">This topic describes a composition of the WS-Atomic Transaction (WS-AT) specification with security and describes the secure binding used for communication between transaction managers.</span></span> <span data-ttu-id="a5d25-118">El enfoque descrito en este documento se ha probado correctamente con otras implementaciones de WS-AT y WS-Coordination incluidos IBM, IONA, Sun Microsystems y otros.</span><span class="sxs-lookup"><span data-stu-id="a5d25-118">The approach described in this document has been successfully tested with other implementations of WS-AT and WS-Coordination including IBM, IONA, Sun Microsystems, and others.</span></span>  
  
 <span data-ttu-id="a5d25-119">En la ilustración siguiente se muestra la interoperabilidad entre dos administradores de transacciones, Transaction Manager 1 y Transaction Manager 2, y dos aplicaciones, Application 1 y Application 2:</span><span class="sxs-lookup"><span data-stu-id="a5d25-119">The following figure depicts the interoperability between two transaction managers, Transaction Manager 1 and Transaction Manager 2, and two applications, Application 1 and Application 2:</span></span>  
  
 ![Captura de pantalla que muestra la interacción entre los administradores de transacciones.](./media/transaction-protocols/transaction-managers-flow.gif)  
  
 <span data-ttu-id="a5d25-121">Considere un escenario típico WS-Coordination/transacciones WS-Atomic con un Iniciador (I) y un Participante (P).</span><span class="sxs-lookup"><span data-stu-id="a5d25-121">Consider a typical WS-Coordination/WS-Atomic Transaction scenario with one Initiator (I) and one Participant (P).</span></span> <span data-ttu-id="a5d25-122">Iniciador y Participante tienen administradores de transacciones (ITM y PTM, respectivamente).</span><span class="sxs-lookup"><span data-stu-id="a5d25-122">Both Initiator and Participant have Transaction Managers, (ITM and PTM, respectively).</span></span> <span data-ttu-id="a5d25-123">La confirmación en dos fases se conoce como 2PC en este tema.</span><span class="sxs-lookup"><span data-stu-id="a5d25-123">Two-phase commit is referred to as 2PC in this topic.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a5d25-124">1. CreateCoordinationContext</span><span class="sxs-lookup"><span data-stu-id="a5d25-124">1. CreateCoordinationContext</span></span>|<span data-ttu-id="a5d25-125">12. respuesta del mensaje de aplicación</span><span class="sxs-lookup"><span data-stu-id="a5d25-125">12. Application Message Response</span></span>|  
|<span data-ttu-id="a5d25-126">2. CreateCoordinationContextResponse</span><span class="sxs-lookup"><span data-stu-id="a5d25-126">2. CreateCoordinationContextResponse</span></span>|<span data-ttu-id="a5d25-127">13. confirmación (finalización)</span><span class="sxs-lookup"><span data-stu-id="a5d25-127">13. Commit (Completion)</span></span>|  
|<span data-ttu-id="a5d25-128">3. registro (finalización)</span><span class="sxs-lookup"><span data-stu-id="a5d25-128">3. Register (Completion)</span></span>|<span data-ttu-id="a5d25-129">14. preparar (2PC)</span><span class="sxs-lookup"><span data-stu-id="a5d25-129">14. Prepare (2PC)</span></span>|  
|<span data-ttu-id="a5d25-130">4. RegisterResponse</span><span class="sxs-lookup"><span data-stu-id="a5d25-130">4. RegisterResponse</span></span>|<span data-ttu-id="a5d25-131">15. preparar (2PC)</span><span class="sxs-lookup"><span data-stu-id="a5d25-131">15. Prepare (2PC)</span></span>|  
|<span data-ttu-id="a5d25-132">5. mensaje de la aplicación</span><span class="sxs-lookup"><span data-stu-id="a5d25-132">5. Application Message</span></span>|<span data-ttu-id="a5d25-133">16. preparado (2PC)</span><span class="sxs-lookup"><span data-stu-id="a5d25-133">16. Prepared (2PC)</span></span>|  
|<span data-ttu-id="a5d25-134">6. CreateCoordinationContext con contexto</span><span class="sxs-lookup"><span data-stu-id="a5d25-134">6. CreateCoordinationContext with Context</span></span>|<span data-ttu-id="a5d25-135">17. preparado (2PC)</span><span class="sxs-lookup"><span data-stu-id="a5d25-135">17. Prepared (2PC)</span></span>|  
|<span data-ttu-id="a5d25-136">7. registro (duradero)</span><span class="sxs-lookup"><span data-stu-id="a5d25-136">7. Register (Durable)</span></span>|<span data-ttu-id="a5d25-137">18. confirmado (finalización)</span><span class="sxs-lookup"><span data-stu-id="a5d25-137">18. Committed (Completion)</span></span>|  
|<span data-ttu-id="a5d25-138">8. RegisterResponse</span><span class="sxs-lookup"><span data-stu-id="a5d25-138">8. RegisterResponse</span></span>|<span data-ttu-id="a5d25-139">19. Commit (2PC)</span><span class="sxs-lookup"><span data-stu-id="a5d25-139">19. Commit (2PC)</span></span>|  
|<span data-ttu-id="a5d25-140">9. CreateCoordinationContextResponse</span><span class="sxs-lookup"><span data-stu-id="a5d25-140">9. CreateCoordinationContextResponse</span></span>|<span data-ttu-id="a5d25-141">20. Commit (2PC)</span><span class="sxs-lookup"><span data-stu-id="a5d25-141">20. Commit (2PC)</span></span>|  
|<span data-ttu-id="a5d25-142">10. registro (duradero)</span><span class="sxs-lookup"><span data-stu-id="a5d25-142">10. Register (Durable)</span></span>|<span data-ttu-id="a5d25-143">21. confirmado (2PC)</span><span class="sxs-lookup"><span data-stu-id="a5d25-143">21. Committed (2PC)</span></span>|  
|<span data-ttu-id="a5d25-144">11. RegisterResponse</span><span class="sxs-lookup"><span data-stu-id="a5d25-144">11. RegisterResponse</span></span>|<span data-ttu-id="a5d25-145">22. confirmado (2PC)</span><span class="sxs-lookup"><span data-stu-id="a5d25-145">22. Committed (2PC)</span></span>|  
  
 <span data-ttu-id="a5d25-146">Este documento describe una composición de la especificación de transacción WS-Atomic con seguridad y describe el enlace seguro utilizado para la comunicación entre administradores de transacciones.</span><span class="sxs-lookup"><span data-stu-id="a5d25-146">This document describes a composition of the WS-AtomicTransaction specification with security and describes the secure binding used for communication between transaction managers.</span></span> <span data-ttu-id="a5d25-147">El enfoque descrito en este documento se ha probado correctamente con otras implementaciones de WS-AT y Coordinación del WS.</span><span class="sxs-lookup"><span data-stu-id="a5d25-147">The approach described in this document has been successfully tested with other implementations of WS-AT and WS-Coordination.</span></span>  
  
 <span data-ttu-id="a5d25-148">La figura y la tabla muestran cuatro clases de mensajes desde el punto de vista de la seguridad:</span><span class="sxs-lookup"><span data-stu-id="a5d25-148">The figure and table illustrate four classes of messages from the viewpoint of security:</span></span>  
  
- <span data-ttu-id="a5d25-149">Mensajes de activación (CreateCoordinationContext y CreateCoordinationContextResponse).</span><span class="sxs-lookup"><span data-stu-id="a5d25-149">Activation messages (CreateCoordinationContext and CreateCoordinationContextResponse).</span></span>  
  
- <span data-ttu-id="a5d25-150">Mensajes del registro (Register y RegisterResponse)</span><span class="sxs-lookup"><span data-stu-id="a5d25-150">Registration messages (Register and RegisterResponse)</span></span>  
  
- <span data-ttu-id="a5d25-151">Mensajes de protocolos (Preparar, Reversión, Confirmar, Anulado, etc.).</span><span class="sxs-lookup"><span data-stu-id="a5d25-151">Protocol messages (Prepare, Rollback, Commit, Aborted, and so on).</span></span>  
  
- <span data-ttu-id="a5d25-152">Mensajes de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="a5d25-152">Application messages.</span></span>  
  
 <span data-ttu-id="a5d25-153">Las primeras tres clases de mensajes están consideradas mensajes de Administrador de transacciones y su configuración de enlaces se describe en el "Intercambio de mensajes de aplicaciones" más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="a5d25-153">The first three message classes are considered Transaction Manager messages and their binding configuration is described in the "Application Message Exchange" later in this topic.</span></span> <span data-ttu-id="a5d25-154">La cuarta clase del mensaje son mensajes de aplicación a aplicación y se describe en la sección “Ejemplos de mensajes” más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="a5d25-154">The fourth class of message is application to application messages and is described in the "Message Examples" section later in this topic.</span></span> <span data-ttu-id="a5d25-155">En esta sección se describen los enlaces de protocolo usados por WCF para cada una de estas clases.</span><span class="sxs-lookup"><span data-stu-id="a5d25-155">This section describes the protocol bindings used for each of these classes by WCF.</span></span>  
  
 <span data-ttu-id="a5d25-156">Los siguientes espacios de nombres XML y prefijos asociados se utilizan a lo largo de este documento.</span><span class="sxs-lookup"><span data-stu-id="a5d25-156">The following XML Namespaces and associated prefixes are used throughout this document.</span></span>  
  
|<span data-ttu-id="a5d25-157">Prefijo</span><span class="sxs-lookup"><span data-stu-id="a5d25-157">Prefix</span></span>|<span data-ttu-id="a5d25-158">Version</span><span class="sxs-lookup"><span data-stu-id="a5d25-158">Version</span></span>|<span data-ttu-id="a5d25-159">Espacio de nombres URI</span><span class="sxs-lookup"><span data-stu-id="a5d25-159">Namespace URI</span></span>|  
|------------|-------------|-------------------|  
|<span data-ttu-id="a5d25-160">s11</span><span class="sxs-lookup"><span data-stu-id="a5d25-160">s11</span></span>||<https://schemas.xmlsoap.org/soap/envelope/>|  
|<span data-ttu-id="a5d25-161">wsa</span><span class="sxs-lookup"><span data-stu-id="a5d25-161">wsa</span></span>|<span data-ttu-id="a5d25-162">Anterior a 1,0</span><span class="sxs-lookup"><span data-stu-id="a5d25-162">Pre-1.0</span></span><br /><br /> <span data-ttu-id="a5d25-163">1.0</span><span class="sxs-lookup"><span data-stu-id="a5d25-163">1.0</span></span>|`http://www.w3.org/2004/08/addressing`<br /><br /> <https://www.w3.org/2005/08/addressing/>|  
|<span data-ttu-id="a5d25-164">wscoor</span><span class="sxs-lookup"><span data-stu-id="a5d25-164">wscoor</span></span>|<span data-ttu-id="a5d25-165">1.0</span><span class="sxs-lookup"><span data-stu-id="a5d25-165">1.0</span></span><br /><br /> <span data-ttu-id="a5d25-166">1.1</span><span class="sxs-lookup"><span data-stu-id="a5d25-166">1.1</span></span>|<http://schemas.xmlsoap.org/ws/2004/10/wscoor/><br /><br /> <https://docs.oasis-open.org/ws-tx/wscoor/2006/06>|  
|<span data-ttu-id="a5d25-167">wsat</span><span class="sxs-lookup"><span data-stu-id="a5d25-167">wsat</span></span>|<span data-ttu-id="a5d25-168">1.0</span><span class="sxs-lookup"><span data-stu-id="a5d25-168">1.0</span></span><br /><br /> <span data-ttu-id="a5d25-169">1.1</span><span class="sxs-lookup"><span data-stu-id="a5d25-169">1.1</span></span>|<http://schemas.xmlsoap.org/ws/2004/10/wsat/><br /><br /> <https://docs.oasis-open.org/ws-tx/wsat/2006/06>|  
|<span data-ttu-id="a5d25-170">m</span><span class="sxs-lookup"><span data-stu-id="a5d25-170">t</span></span>|<span data-ttu-id="a5d25-171">Pre-1.3</span><span class="sxs-lookup"><span data-stu-id="a5d25-171">Pre-1.3</span></span><br /><br /> <span data-ttu-id="a5d25-172">1.3</span><span class="sxs-lookup"><span data-stu-id="a5d25-172">1.3</span></span>|<http://schemas.xmlsoap.org/ws/2005/02/trust/><br /><br /> <https://docs.oasis-open.org/ws-sx/ws-trust/200512>|  
|<span data-ttu-id="a5d25-173">o</span><span class="sxs-lookup"><span data-stu-id="a5d25-173">o</span></span>||<https://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd>|  
|<span data-ttu-id="a5d25-174">xsd</span><span class="sxs-lookup"><span data-stu-id="a5d25-174">xsd</span></span>||<https://www.w3.org/2001/XMLSchema>|  
  
## <a name="transaction-manager-bindings"></a><span data-ttu-id="a5d25-175">Enlaces del administrador de transacciones</span><span class="sxs-lookup"><span data-stu-id="a5d25-175">Transaction Manager Bindings</span></span>  
 <span data-ttu-id="a5d25-176">R1001: los administradores de transacciones que participan en una transacción WS-AT 1,0 deben usar SOAP 1,1 y WS-Addressing 2004/08 para los intercambios de mensajes WS-Atomic Transaction y WS-Coordination.</span><span class="sxs-lookup"><span data-stu-id="a5d25-176">R1001: Transaction Managers participating in a WS-AT 1.0 transaction must use SOAP 1.1 and WS-Addressing 2004/08 for WS-Atomic Transaction and WS-Coordination message exchanges.</span></span>  
  
 <span data-ttu-id="a5d25-177">R1002: los administradores de transacciones que participan en una transacción WS-AT 1.1 deben utilizar SOAP 1.1 y WS-Addressing 2005/08 para intercambios de mensajes de transacciones WS-Atomic y WS-Coordination.</span><span class="sxs-lookup"><span data-stu-id="a5d25-177">R1002: Transaction Managers participating in a WS-AT 1.1 transaction must use SOAP 1.1 and WS-Addressing 2005/08 for WS-Atomic Transaction and WS-Coordination message exchanges.</span></span>  
  
 <span data-ttu-id="a5d25-178">Los mensajes de la aplicación no se restringen a estos enlaces y se describen más adelante.</span><span class="sxs-lookup"><span data-stu-id="a5d25-178">Application messages are not constrained to these bindings and are described later.</span></span>  
  
### <a name="transaction-manager-https-binding"></a><span data-ttu-id="a5d25-179">Enlace HTTPS de administrador de transacciones</span><span class="sxs-lookup"><span data-stu-id="a5d25-179">Transaction Manager HTTPS Binding</span></span>  
 <span data-ttu-id="a5d25-180">El enlace HTTPS del administrador de transacciones confía solamente en la seguridad de transporte para lograr la seguridad y establecer confianza entre cada par de remitente-receptor en el árbol de transacciones.</span><span class="sxs-lookup"><span data-stu-id="a5d25-180">The transaction manager HTTPS binding relies solely on transport security to achieve security and establish trust between each sender-receiver pair in the transaction tree.</span></span>  
  
#### <a name="https-transport-configuration"></a><span data-ttu-id="a5d25-181">Configuración de transporte HTTPS</span><span class="sxs-lookup"><span data-stu-id="a5d25-181">HTTPS Transport Configuration</span></span>  
 <span data-ttu-id="a5d25-182">Los certificados X.509 se utilizan para establecer la identidad del administrador de transacciones.</span><span class="sxs-lookup"><span data-stu-id="a5d25-182">X.509 certificates are used to establish Transaction Manager Identity.</span></span> <span data-ttu-id="a5d25-183">Se requiere la autenticación cliente/servidor, y la autorización cliente/servidor queda como un detalle de implementación:</span><span class="sxs-lookup"><span data-stu-id="a5d25-183">Client/server authentication is required, and client/server authorization is left as an implementation detail:</span></span>  
  
- <span data-ttu-id="a5d25-184">R1111: los certificados X.509 presentados a través de la conexión deben tener un nombre de sujeto que coincida con el nombre de dominio completo (FQDN) del equipo de origen.</span><span class="sxs-lookup"><span data-stu-id="a5d25-184">R1111: X.509 certificates presented over the wire must have a subject name that matches the fully qualified domain name (FQDN) of the originating machine.</span></span>  
  
- <span data-ttu-id="a5d25-185">B1112: DNS debe ser funcional entre cada par remitente-receptor del sistema para que las comprobaciones de nombre de sujeto X.509 se realicen correctamente.</span><span class="sxs-lookup"><span data-stu-id="a5d25-185">B1112: DNS must be functional between each sender-receiver pair in the system for X.509 subject name checks to succeed.</span></span>  
  
#### <a name="activation-and-registration-binding-configuration"></a><span data-ttu-id="a5d25-186">Activación y configuración de enlace de registro</span><span class="sxs-lookup"><span data-stu-id="a5d25-186">Activation and Registration Binding Configuration</span></span>  
 <span data-ttu-id="a5d25-187">WCF requiere un enlace dúplex de solicitud/respuesta con correlación sobre HTTPS.</span><span class="sxs-lookup"><span data-stu-id="a5d25-187">WCF requires request/reply duplex binding with correlation over HTTPS.</span></span> <span data-ttu-id="a5d25-188">(Para obtener más información sobre la correlación y descripciones de los patrones de intercambio de mensajes de solicitud/respuesta, vea Transacción WS-Atomic, sección 8.)</span><span class="sxs-lookup"><span data-stu-id="a5d25-188">(For more information about correlation and descriptions of the request/reply message exchange patterns, see WS-Atomic Transaction, Section 8.)</span></span>  
  
#### <a name="2pc-protocol-binding-configuration"></a><span data-ttu-id="a5d25-189">Configuración de enlace de protocolo 2PC</span><span class="sxs-lookup"><span data-stu-id="a5d25-189">2PC Protocol Binding Configuration</span></span>  
 <span data-ttu-id="a5d25-190">WCF admite mensajes unidireccionales (datagrama) a través de HTTPS.</span><span class="sxs-lookup"><span data-stu-id="a5d25-190">WCF supports one-way (datagram) messages over HTTPS.</span></span> <span data-ttu-id="a5d25-191">La correlación entre los mensajes queda como un detalle de implementación.</span><span class="sxs-lookup"><span data-stu-id="a5d25-191">Correlation among the messages is left as an implementation detail.</span></span>  
  
 <span data-ttu-id="a5d25-192">B1131: las implementaciones deben admitir `wsa:ReferenceParameters` tal y como se describe en WS-Addressing para lograr la correlación de los mensajes 2PC de WCF.</span><span class="sxs-lookup"><span data-stu-id="a5d25-192">B1131: Implementations must support `wsa:ReferenceParameters` as described in WS-Addressing to achieve correlation of WCF’s 2PC messages.</span></span>  
  
### <a name="transaction-manager-mixed-security-binding"></a><span data-ttu-id="a5d25-193">Enlace de seguridad mixta del administrador de transacciones</span><span class="sxs-lookup"><span data-stu-id="a5d25-193">Transaction Manager Mixed Security Binding</span></span>  
 <span data-ttu-id="a5d25-194">Éste es un enlace alternativo (modo mixto) que utiliza seguridad de transporte combinada con el modelo de token emitido de WS-Coordination para el establecimiento de la identidad.</span><span class="sxs-lookup"><span data-stu-id="a5d25-194">This is an alternate (mixed mode) binding that uses transport security combined with the WS-Coordination Issued Token model for identity establishment purposes.</span></span> <span data-ttu-id="a5d25-195">La activación y el registro son los únicos elementos que difieren entre los dos enlaces.</span><span class="sxs-lookup"><span data-stu-id="a5d25-195">Activation and Registration are the only elements that differ between the two bindings.</span></span>  
  
#### <a name="https-transport-configuration"></a><span data-ttu-id="a5d25-196">Configuración de transporte HTTPS</span><span class="sxs-lookup"><span data-stu-id="a5d25-196">HTTPS Transport Configuration</span></span>  
 <span data-ttu-id="a5d25-197">Los certificados X.509 se utilizan para establecer la identidad del administrador de transacciones.</span><span class="sxs-lookup"><span data-stu-id="a5d25-197">X.509 certificates are used to establish Transaction Manager Identity.</span></span> <span data-ttu-id="a5d25-198">Se requiere la autenticación cliente/servidor, y la autorización cliente/servidor queda como un detalle de implementación.</span><span class="sxs-lookup"><span data-stu-id="a5d25-198">Client/Server authentication is required, and client/server authorization is left as an implementation detail.</span></span>  
  
#### <a name="activation-message-binding-configuration"></a><span data-ttu-id="a5d25-199">Configuración del enlace de mensajes de activación</span><span class="sxs-lookup"><span data-stu-id="a5d25-199">Activation Message Binding Configuration</span></span>  
 <span data-ttu-id="a5d25-200">Los mensajes de activación normalmente no participan en la interoperabilidad porque, por lo general, se producen entre una aplicación y su administrador de transacción local.</span><span class="sxs-lookup"><span data-stu-id="a5d25-200">Activation Messages usually do not participate in interoperability because they typically occur between an application and its local Transaction Manager.</span></span>  
  
 <span data-ttu-id="a5d25-201">B1221: WCF usa el enlace HTTPS dúplex (descrito en [protocolos de mensajería](../../../../docs/framework/wcf/feature-details/messaging-protocols.md)) para los mensajes de activación.</span><span class="sxs-lookup"><span data-stu-id="a5d25-201">B1221: WCF uses duplex HTTPS binding (described in [Messaging Protocols](../../../../docs/framework/wcf/feature-details/messaging-protocols.md)) for Activation messages.</span></span> <span data-ttu-id="a5d25-202">Los mensajes de solicitud y respuesta se ponen en correlación utilizando WS-Addressing 2004/08 para WS-AT 1.0 y WS-Addressing 2005/08 para WS-AT 1.1.</span><span class="sxs-lookup"><span data-stu-id="a5d25-202">Request and Reply messages are correlated using WS-Addressing 2004/08 for WS-AT 1.0 and WS-Addressing 2005/08 for WS-AT 1.1.</span></span>  
  
 <span data-ttu-id="a5d25-203">La especificación de transacción WS-Atomic, sección 8, describe detalles adicionales sobre la correlación y los patrones de intercambio de mensajes.</span><span class="sxs-lookup"><span data-stu-id="a5d25-203">WS-Atomic Transaction specification, Section 8, describes further details about correlation and the message exchange patterns.</span></span>  
  
- <span data-ttu-id="a5d25-204">R1222: tras recibir `CreateCoordinationContext`, el coordinador debe emitir un `SecurityContextToken` con `STx`secreto asociado.</span><span class="sxs-lookup"><span data-stu-id="a5d25-204">R1222: Upon receiving a `CreateCoordinationContext`, the Coordinator must issue a `SecurityContextToken` with associated secret `STx`.</span></span> <span data-ttu-id="a5d25-205">Este token se devuelve dentro de un encabezado `t:IssuedTokens` que sigue la especificación de WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="a5d25-205">This token is returned inside a `t:IssuedTokens` header following WS-Trust specification.</span></span>  
  
- <span data-ttu-id="a5d25-206">R1223: si la activación se produce dentro de un contexto de coordinación existente, el encabezado `t:IssuedTokens` con el `SecurityContextToken` asociado al contexto existente debe fluir en el mensaje `CreateCoordinationContext`.</span><span class="sxs-lookup"><span data-stu-id="a5d25-206">R1223: If Activation occurs within an existing Coordination Context, the `t:IssuedTokens` header with the `SecurityContextToken` associated with existing Context must flow on the `CreateCoordinationContext` message.</span></span>  
  
 <span data-ttu-id="a5d25-207">Se debe generar un nuevo encabezado de `t:IssuedTokens` para adjuntar al mensaje de `wscoor:CreateCoordinationContextResponse` saliente.</span><span class="sxs-lookup"><span data-stu-id="a5d25-207">A new `t:IssuedTokens` header should be generated for attaching to the outgoing `wscoor:CreateCoordinationContextResponse` message.</span></span>  
  
#### <a name="registration-message-binding-configuration"></a><span data-ttu-id="a5d25-208">Configuración del enlace de mensajes de registro</span><span class="sxs-lookup"><span data-stu-id="a5d25-208">Registration Message Binding Configuration</span></span>  
 <span data-ttu-id="a5d25-209">B1231: WCF usa el enlace HTTPS dúplex (descrito en [protocolos de mensajería](../../../../docs/framework/wcf/feature-details/messaging-protocols.md)).</span><span class="sxs-lookup"><span data-stu-id="a5d25-209">B1231: WCF uses duplex HTTPS binding (described in [Messaging Protocols](../../../../docs/framework/wcf/feature-details/messaging-protocols.md)).</span></span> <span data-ttu-id="a5d25-210">Los mensajes de solicitud y respuesta se ponen en correlación utilizando WS-Addressing 2004/08 para WS-AT 1.0 y WS-Addressing 2005/08 para WS-AT 1.1.</span><span class="sxs-lookup"><span data-stu-id="a5d25-210">Request and Reply messages are correlated using WS-Addressing 2004/08 for WS-AT 1.0 and WS-Addressing 2005/08 for WS-AT 1.1.</span></span>  
  
 <span data-ttu-id="a5d25-211">La transacción WS-Atomic, sección 8, describe detalles adicionales sobre la correlación y las descripciones del patrón de intercambio de mensajes.</span><span class="sxs-lookup"><span data-stu-id="a5d25-211">WS-AtomicTransaction, Section 8, describes further details about correlation and descriptions of the message exchange patterns.</span></span>  
  
 <span data-ttu-id="a5d25-212">R1232: los mensajes de `wscoor:Register` salientes deben usar el modo de autenticación `IssuedTokenOverTransport` descrito en [protocolos de seguridad](../../../../docs/framework/wcf/feature-details/security-protocols.md).</span><span class="sxs-lookup"><span data-stu-id="a5d25-212">R1232: Outgoing `wscoor:Register` messages must use the `IssuedTokenOverTransport` authentication mode described in [Security Protocols](../../../../docs/framework/wcf/feature-details/security-protocols.md).</span></span>  
  
 <span data-ttu-id="a5d25-213">El elemento `wsse:Timestamp` se debe firmar utilizando el `SecurityContextToken STx` emitido.</span><span class="sxs-lookup"><span data-stu-id="a5d25-213">The `wsse:Timestamp` element must be signed using the `SecurityContextToken STx` issued.</span></span> <span data-ttu-id="a5d25-214">Esta firma es una prueba de posesión del token asociado a la transacción determinada y se utiliza para autenticar a un participante enumerado en la transacción.</span><span class="sxs-lookup"><span data-stu-id="a5d25-214">This signature is a proof of possession of the token associated with particular transaction and is used to authenticate a participant enlisting in the transaction.</span></span> <span data-ttu-id="a5d25-215">El mensaje RegistrationResponse se devuelve sobre HTTPS.</span><span class="sxs-lookup"><span data-stu-id="a5d25-215">The RegistrationResponse message is sent back over HTTPS.</span></span>  
  
#### <a name="2pc-protocol-binding-configuration"></a><span data-ttu-id="a5d25-216">Configuración de enlace de protocolo 2PC</span><span class="sxs-lookup"><span data-stu-id="a5d25-216">2PC Protocol Binding Configuration</span></span>  
 <span data-ttu-id="a5d25-217">WCF admite mensajes unidireccionales (datagrama) a través de HTTPS.</span><span class="sxs-lookup"><span data-stu-id="a5d25-217">WCF supports one-way (datagram) messages over HTTPS.</span></span> <span data-ttu-id="a5d25-218">La correlación entre los mensajes queda como un detalle de implementación.</span><span class="sxs-lookup"><span data-stu-id="a5d25-218">Correlation among the messages is left as an implementation detail.</span></span>  
  
 <span data-ttu-id="a5d25-219">B1241: las implementaciones deben admitir `wsa:ReferenceParameters` tal y como se describe en WS-Addressing para lograr la correlación de los mensajes 2PC de WCF.</span><span class="sxs-lookup"><span data-stu-id="a5d25-219">B1241: Implementations must support `wsa:ReferenceParameters` as described in WS-Addressing to achieve correlation of WCF’s 2PC messages.</span></span>  
  
## <a name="application-message-exchange"></a><span data-ttu-id="a5d25-220">Intercambio de mensajes de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="a5d25-220">Application Message Exchange</span></span>  
 <span data-ttu-id="a5d25-221">Las aplicaciones pueden utilizar cualquier enlace determinado para los mensajes de aplicación a aplicación, con tal de que el enlace cumpla los siguientes requisitos de seguridad:</span><span class="sxs-lookup"><span data-stu-id="a5d25-221">Applications are free to use any particular binding for application-to-application messages, as long as the binding meets the following security requirements:</span></span>  
  
- <span data-ttu-id="a5d25-222">R2001: los mensajes de aplicación a aplicación deben fluir el encabezado `t:IssuedTokens` junto con `CoordinationContext` en el encabezado del mensaje.</span><span class="sxs-lookup"><span data-stu-id="a5d25-222">R2001: Application-to-application messages must flow the `t:IssuedTokens` header along with the `CoordinationContext` in the header of the message.</span></span>  
  
- <span data-ttu-id="a5d25-223">R2002: se debe proporcionar la integridad y confidencialidad de `t:IssuedToken`.</span><span class="sxs-lookup"><span data-stu-id="a5d25-223">R2002: Integrity and confidentiality of `t:IssuedToken` must be provided.</span></span>  
  
 <span data-ttu-id="a5d25-224">El encabezado `CoordinationContext` contiene `wscoor:Identifier`.</span><span class="sxs-lookup"><span data-stu-id="a5d25-224">The `CoordinationContext` header contains `wscoor:Identifier`.</span></span> <span data-ttu-id="a5d25-225">Aunque la definición de `xsd:AnyURI` permite el uso de URI absolutos y relativos, WCF solo admite `wscoor:Identifiers`, que son URI absolutos.</span><span class="sxs-lookup"><span data-stu-id="a5d25-225">While the definition of `xsd:AnyURI` allows the use of both absolute and relative URIs, WCF supports only `wscoor:Identifiers`, which are absolute URIs.</span></span>  
  
 <span data-ttu-id="a5d25-226">B2003: Si el `wscoor:Identifier` de la `wscoor:CoordinationContext` es un URI relativo, los errores se devolverán desde los servicios de WCF transaccionales.</span><span class="sxs-lookup"><span data-stu-id="a5d25-226">B2003: If the `wscoor:Identifier` of the `wscoor:CoordinationContext` is a relative URI, faults will be returned from transactional WCF services.</span></span>  
  
## <a name="message-examples"></a><span data-ttu-id="a5d25-227">Ejemplos de mensajes</span><span class="sxs-lookup"><span data-stu-id="a5d25-227">Message Examples</span></span>  
  
### <a name="createcoordinationcontext-requestresponse-messages"></a><span data-ttu-id="a5d25-228">Mensajes de solicitud/respuesta CreateCoordinationContext</span><span class="sxs-lookup"><span data-stu-id="a5d25-228">CreateCoordinationContext Request/Response Messages</span></span>  
 <span data-ttu-id="a5d25-229">Los siguientes mensajes siguen un patrón de solicitud/respuesta.</span><span class="sxs-lookup"><span data-stu-id="a5d25-229">The following messages follow a request/response pattern.</span></span>  
  
#### <a name="createcoordinationcontext-with-wscoor-10"></a><span data-ttu-id="a5d25-230">CreateCoordinationContext con WSCoor 1,0</span><span class="sxs-lookup"><span data-stu-id="a5d25-230">CreateCoordinationContext with WSCoor 1.0</span></span>  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <a:Action>http://.../ws/2004/10/wscoor/CreateCoordinationContext</Action>  
    <a:MessageID>urn:uuid:069f5104-fd88-4264-9f99-60032a82854e</MessageID>  
    <a:ReplyTo>  
      <Address>https://...</a:Address>  
    </a:ReplyTo>  
    <a:To>https://...</a:To>  
    <wsse:Security>  
      <u:Timestamp>  
        <wsu:Created>2005-12-15T23:36:09.921Z</u:Created>  
        <wsu:Expires>2005-12-15T23:41:09.921Z</u:Expires>  
      </u:Timestamp>  
    </wsse:Security>  
  </s:Header>  
  <s:Body xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">  
    <wscoor:CreateCoordinationContext>  
      <wscoor:CoordinationType>...</wscoor:CoordinationType>  
    </wscoor:CreateCoordinationContext>  
  </s:Body>  
</s11:Envelope>  
```  
  
#### <a name="createcoordinationcontext-with-wscoor-11"></a><span data-ttu-id="a5d25-231">CreateCoordinationContext con WSCoor 1.1</span><span class="sxs-lookup"><span data-stu-id="a5d25-231">CreateCoordinationContext with WSCoor 1.1</span></span>  
  
```xml  
<s:Envelope>   
<s:Header>  
<a:Action>http://docs.oasis-open.org/ws-tx/wscoor/2006/06/CreateCoordinationContext</Action>  
<a:MessageID>urn:uuid:069f5104-fd88-4264-9f99-60032a82854e</MessageID>  
<a:ReplyTo>   
<Address>https://...</a:Address>   
</a:ReplyTo>   
<a:To>https://...</a:To>   
<wsse:Security>  
 <u:Timestamp>  
<wsu:Created>2005-12-15T23:36:09.921Z</u:Created>  
<wsu:Expires>2005-12-15T23:41:09.921Z</u:Expires>  
</u:Timestamp>   
</wsse:Security>   
</s:Header>   
<s:Body xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">  
<wscoor:CreateCoordinationContext>  
<wscoor:CoordinationType>...</wscoor:CoordinationType>  
</wscoor:CreateCoordinationContext>  
 </s:Body>  
</s11:Envelope>  
```  
  
#### <a name="createcoordinationcontextresponse-with-trust-pre-13-and-wscoor-10"></a><span data-ttu-id="a5d25-232">CreateCoordinationContextResponse con Trust Pre-1.3 y WSCoor 1.0</span><span class="sxs-lookup"><span data-stu-id="a5d25-232">CreateCoordinationContextResponse with Trust Pre-1.3 and WSCoor 1.0</span></span>  
  
```xml  
<s:Envelope>  
  <!-- Data below is shown in the clear for  
       illustration purposes only. -->  
  <s:Header>  
    <a:Action>./ws/2004/10/wscoor/CreateCoordinationContextResponse </a:Action>  
    <a:RelatesTo>urn:uuid:069f5104-fd88-4264-9f99-60032a82854e</a:RelatesTo>  
    <a:To s:mustUnderstand="1">https://... </a:To>  
    <t:IssuedTokens>  
 <wst:RequestSecurityTokenResponse     
    xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"  
    xmlns:wssu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd"   
    xmlns:wst="http://schemas.xmlsoap.org/ws/2005/02/trust"  
    xmlns:wsc="http://schemas.xmlsoap.org/ws/2005/02/sc"  
    xmlns:wsp="http://schemas.xmlsoap.org/ws/2004/09/policy">  
    <wst:TokenType>http://schemas.xmlsoap.org/ws/2005/02/sc/sct</wst:TokenType>  
    <wst:RequestedSecurityToken>  
      <wsc:SecurityContextToken>  
        <wssu:Identifier>  
          http://fabrikam123.com/SCTi  
        </wssu:Identifier>  
      </wsc:SecurityContextToken>   
    </wst:RequestedSecurityToken>  
    <wsp:AppliesTo>  
        http://fabrikam123.com/CCi  
    </wsp:AppliesTo>    
    <wst:RequestedAttachedReference>  
      <wsse:SecurityTokenReference >  
        <wsse:Reference   
           ValueType="http://schemas.xmlsoap.org/ws/2005/02/sc/sct"  
           URI="http://fabrikam123.com/SCTi"/>  
      </wsse:SecurityTokenReference>  
    </wst:RequestedAttachedReference>  
    <wst:RequestedUnattachedReference>  
      <wsse:SecurityTokenReference>  
        <wsse:Reference   
          ValueType="http://schemas.xmlsoap.org/ws/2005/02/sc/sct"  
          URI="http://fabrikam123.com/SCTi"/>  
      </wsse:SecurityTokenReference>  
    </wst:RequestedUnattachedReference>  
    <wst:RequestedProofToken>  
      <wst:BinarySecret   
        Type="http://schemas.xmlsoap.org/ws/2005/02/trust/SymmetricKey">  
        <!-- base64 encoded value -->  
      </wst:BinarySecret>  
    </wst:RequestedProofToken>  
    <wst:Lifetime>  
      <wssu:Created>2005-10-24T20:19:26.526Z</wssu:Created>  
      <wssu:Expires>2005-10-25T06:24:26.526Z</wssu:Expires>  
    </wst:Lifetime>  
    <wst:KeySize>256</wst:KeySize>  
</wst:RequestSecurityTokenResponse>  
    </t:IssuedTokens>  
    <o:Security xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">  
      <u:Timestamp u:Id="_0">  
        <u:Created>2005-12-15T23:36:12.015Z</u:Created>  
        <u:Expires>2005-12-15T23:41:12.015Z</u:Expires>  
      </u:Timestamp>  
    </o:Security>  
  </s:Header>  
  <s:Body>  
    <wscoor:CreateCoordinationContextResponse>  
      <wscoor:CoordinationContext>  
        <wscoor:Identifier>  
     http://fabrikam123.com/CCi  
      </wscoor:Identifier>  
        <wscoor:Expires>...</wscoor:Expires>  
        <wscoor:CoordinationType>...</wscoor:CoordinationType>  
        <wscoor:RegistrationService>  
          <a:Address>https://...</a:Address>  
          <a:ReferenceParameters>  
             ...  
          </a:ReferenceParameters>  
        </wscoor:RegistrationService>  
      </wscoor:CoordinationContext>  
    </wscoor:CreateCoordinationContextResponse>  
  </s:Body>  
</s:Envelope>  
```  
  
#### <a name="createcoordinationcontextresponse-with-trust-13-and-wscoor-11"></a><span data-ttu-id="a5d25-233">CreateCoordinationContextResponse con Trust 1.3 y WSCoor 1.1</span><span class="sxs-lookup"><span data-stu-id="a5d25-233">CreateCoordinationContextResponse with Trust 1.3 and WSCoor 1.1</span></span>  
  
```xml  
<s:Envelope>  
<!-- Data below is shown in the clear for illustration purposes only. -->   
<s:Header>   
<a:Action>http://docs.oasis-open.org/ws-tx/wscoor/2006/06/CreateCoordinationContextResponse </a:Action>  
<a:RelatesTo>urn:uuid:069f5104-fd88-4264-9f99-60032a82854e</a:RelatesTo>  
<a:To s:mustUnderstand="1">https://... </a:To>   
<t:IssuedTokens>   
<wst:RequestSecurityTokenResponse   
xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"   
xmlns:wssu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd"   
xmlns:wst="http://docs.oasis-open.org/ws-sx/ws-trust/200512"  
xmlns:wsc="http://schemas.xmlsoap.org/ws/2005/02/sc"  
xmlns:wsp="http://schemas.xmlsoap.org/ws/2004/09/policy">  
<wst:TokenType>http://schemas.xmlsoap.org/ws/2005/02/sc/sct</wst:TokenType>  
<wst:RequestedSecurityToken>   
<wsc:SecurityContextToken>   
<wssu:Identifier> http://fabrikam123.com/SCTi  
</wssu:Identifier>   
</wsc:SecurityContextToken>   
</wst:RequestedSecurityToken>   
<wsp:AppliesTo> http://fabrikam123.com/CCi </wsp:AppliesTo>  
<wst:RequestedAttachedReference>   
<wsse:SecurityTokenReference >   
<wsse:Reference  
  ValueType="http://schemas.xmlsoap.org/ws/2005/02/sc/sct"  
  URI="http://fabrikam123.com/SCTi"/>  
</wsse:SecurityTokenReference>   
</wst:RequestedAttachedReference>   
<wst:RequestedUnattachedReference>   
<wsse:SecurityTokenReference>   
<wsse:Reference  
 ValueType="http://schemas.xmlsoap.org/ws/2005/02/sc/sct"  
 URI="http://fabrikam123.com/SCTi"/>  
</wsse:SecurityTokenReference>   
</wst:RequestedUnattachedReference>   
<wst:RequestedProofToken>   
<wst:BinarySecret  
  Type="http://docs.oasis-open.org/ws-sx/ws-trust/200512/SymmetricKey">  
  <!-- base64 encoded value -->   
</wst:BinarySecret>   
</wst:RequestedProofToken>   
<wst:Lifetime>   
<wssu:Created>2005-10-24T20:19:26.526Z</wssu:Created>  
<wssu:Expires>2005-10-25T06:24:26.526Z</wssu:Expires>  
</wst:Lifetime>   
<wst:KeySize>256</wst:KeySize>   
</wst:RequestSecurityTokenResponse>   
</t:IssuedTokens>   
<o:Security xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">   
<u:Timestamp u:Id="_0">   
<u:Created>2005-12-15T23:36:12.015Z</u:Created>   
<u:Expires>2005-12-15T23:41:12.015Z</u:Expires>   
</u:Timestamp>   
</o:Security>   
</s:Header>   
<s:Body>   
<wscoor:CreateCoordinationContextResponse>   
<wscoor:CoordinationContext>   
<wscoor:Identifier> http://fabrikam123.com/CCi  
</wscoor:Identifier>   
<wscoor:Expires>...</wscoor:Expires>  
<wscoor:CoordinationType>...</wscoor:CoordinationType>  
<wscoor:RegistrationService>   
<a:Address>https://...</a:Address>  
<a:ReferenceParameters> ...  
</a:ReferenceParameters>  
</wscoor:RegistrationService>   
</wscoor:CoordinationContext>   
</wscoor:CreateCoordinationContextResponse>   
</s:Body>   
</s:Envelope>  
```  
  
### <a name="registration-messages"></a><span data-ttu-id="a5d25-234">Mensajes del registro</span><span class="sxs-lookup"><span data-stu-id="a5d25-234">Registration Messages</span></span>  
 <span data-ttu-id="a5d25-235">Los siguientes mensajes son mensajes del registro.</span><span class="sxs-lookup"><span data-stu-id="a5d25-235">The following messages are registration messages.</span></span>  
  
#### <a name="register-with-wscoor-10"></a><span data-ttu-id="a5d25-236">Regístrese con WSCoor 1,0</span><span class="sxs-lookup"><span data-stu-id="a5d25-236">Register with WSCoor 1.0</span></span>  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <a:Action>http://schemas.xmlsoap.org/ws/2004/10/wscoor/Register</a:Action>  
    <a:MessageID>urn:uuid:ed418b86-a75e-4aea-9d4e-a5d0cb5c088e</a:MessageID>  
    <a:ReplyTo>  
      <a:Address>https://...</a:Address>        
    </a:ReplyTo>  
    <a:To>https://...</a:To>  
    <wsse:Security   
      s:mustUnderstand="1"   
      xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"  
      xmlns:wssu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">  
      <wssu:Timestamp wssu:Id="_0" >  
        <wssu:Created>2005-12-15T23:36:13.827Z</wssu:Created>  
        <wssu:Expires>2005-12-15T23:41:13.827Z</wssu:Expires>  
      </wssu:Timestamp>  
      <wsc:SecurityContextToken>  
      <wssu:Identifier>  
          http://fabrikam123.com/SCTi  
      </wssu:Identifier>  
      </wsc:SecurityContextToken>  
      <!-- supporting signature over the timestamp -->  
      <wsse:Signature xmlns:ds="http://www.w3.org/2000/09/xmldsig#">  
        <ds:SignedInfo>  
          <ds:CanonicalizationMethod Algorithm="http://www.w3.org/2001/10/xml-exc-c14n#"/>  
          <ds:SignatureMethod Algorithm="http://www.w3.org/2000/09/xmldsig#hmac-sha1"/>  
          <ds:Reference URI="#_0">  
            <ds:Transforms>  
              <ds:Transform Algorithm="http://www.w3.org/2001/10/xml-exc-c14n#"/>  
            </ds:Transforms>  
            <ds:DigestMethod Algorithm="http://www.w3.org/2000/09/xmldsig#sha1"/>  
            <ds:DigestValue>  
              alRzyhjLgoUOYoh8cx4n75eTcUk=  
            </ds:DigestValue>  
          </ds:Reference>  
        </ds:SignedInfo>  
        <ds:SignatureValue>YZYjnVvSOVasAQqQxaaviTSWtqI=</ds:SignatureValue>  
        <ds:KeyInfo>  
          <wsse:SecurityTokenReference  
            xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">  
            <wsse:Reference   
              URI="http://fabrikam123.com/SCTi"/>  
          </wsse:SecurityTokenReference>  
        </ds:KeyInfo>  
      </wsse:Signature>  
    </wsse:Security>  
  </s:Header>  
  <s:Body xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">  
    <wscoor:Register>  
      <wscoor:ProtocolIdentifier>...</wscoor:ProtocolIdentifier>  
      <wscoor:ParticipantProtocolService>  
        <a:Address>https://... </a:Address>  
      </wscoor:ParticipantProtocolService>  
    </wscoor:Register>  
  </s:Body>  
</s:Envelope>  
```  
  
#### <a name="register-with-wscoor-11"></a><span data-ttu-id="a5d25-237">Registro con WSCoor 1.1</span><span class="sxs-lookup"><span data-stu-id="a5d25-237">Register with WSCoor 1.1</span></span>  
  
```xml  
<s:Envelope>  
<s:Header>   
<a:Action>http://docs.oasis-open.org/ws-tx/wscoor/2006/06/Register</a:Action>   
<a:MessageID>urn:uuid:ed418b86-a75e-4aea-9d4e-a5d0cb5c088e</a:MessageID>  
<a:ReplyTo>   
<a:Address>https://...</a:Address>   
</a:ReplyTo>  
<a:To>https://...</a:To>   
<wsse:Security   
s:mustUnderstand="1"   
xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"   
xmlns:wssu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">  
<wssu:Timestamp wssu:Id="_0" >   
<wssu:Created>2005-12-15T23:36:13.827Z</wssu:Created>  
<wssu:Expires>2005-12-15T23:41:13.827Z</wssu:Expires>  
</wssu:Timestamp>   
<wsc:SecurityContextToken>   
<wssu:Identifier> http://fabrikam123.com/SCTi  
</wssu:Identifier>   
</wsc:SecurityContextToken>   
<!-- supporting signature over the timestamp -->  
<wsse:Signature xmlns:ds="http://www.w3.org/2000/09/xmldsig#">  
<ds:SignedInfo>   
<ds:CanonicalizationMethod Algorithm="http://www.w3.org/2001/10/xml-exc-c14n#"/>   
<ds:SignatureMethod Algorithm="http://www.w3.org/2000/09/xmldsig#hmac-sha1"/>   
<ds:Reference URI="#_0">   
<ds:Transforms>   
<ds:Transform Algorithm="http://www.w3.org/2001/10/xml-exc-c14n#"/>   
</ds:Transforms>   
<ds:DigestMethod  
Algorithm="http://www.w3.org/2000/09/xmldsig#sha1"/>   
<ds:DigestValue> alRzyhjLgoUOYoh8cx4n75eTcUk=  
</ds:DigestValue>   
</ds:Reference>   
</ds:SignedInfo>  
<ds:SignatureValue>YZYjnVvSOVasAQqQxaaviTSWtqI=  
</ds:SignatureValue>  
<ds:KeyInfo>   
<wsse:SecurityTokenReference xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">  
  <wsse:Reference URI="http://fabrikam123.com/SCTi"/>  
</wsse:SecurityTokenReference>   
</ds:KeyInfo>   
</wsse:Signature>   
</wsse:Security>   
</s:Header>   
<s:Body xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">   
<wscoor:Register>   
<wscoor:ProtocolIdentifier>...</wscoor:ProtocolIdentifier>  
<wscoor:ParticipantProtocolService>   
<a:Address>https://... </a:Address>  
</wscoor:ParticipantProtocolService>   
</wscoor:Register>   
</s:Body>   
</s:Envelope>  
```  
  
#### <a name="register-response-with-wscoor-10"></a><span data-ttu-id="a5d25-238">Registrar respuesta con WSCoor 1,0</span><span class="sxs-lookup"><span data-stu-id="a5d25-238">Register Response with WSCoor 1.0</span></span>  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <a:Action>  
      http://schemas.xmlsoap.org/ws/2004/10/wscoor/RegisterResponse  
    </a:Action>  
    <a:MessageID>urn:uuid:ed418b86-a75e-4aea-9d4e-a5d0cb5c088d</a:MessageID>  
    <a:RelatesTo>  
      urn:uuid:ed418b86-a75e-4aea-9d4e-a5d0cb5c088e        
    </a:RelatesTo>  
    <a:To>https://...</a:To>  
    <wsse:Security   
      s:mustUnderstand="1"   
      xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"  
      xmlns:wssu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">  
      <wssu:Timestamp>  
        <wssu:Created>2005-12-15T23:36:13.827Z</wssu:Created>  
        <wssu:Expires>2005-12-15T23:41:13.827Z</wssu:Expires>  
      </wssu:Timestamp>  
    </wsse:Security>  
  </s:Header>  
  <s:Body xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">  
    <wscoor:RegisterResponse>  
      <wscoor:CoordinatorProtocolService>  
        <a:Address>https://...</a:Address>  
        <a:ReferenceParameters>  
          ...  
        </a:ReferenceParameters>  
      </wscoor:CoordinatorProtocolService>  
    </wscoor:RegisterResponse>  
  </s:Body>  
</s:Envelope>  
```  
  
#### <a name="register-response-with-wscoor-11"></a><span data-ttu-id="a5d25-239">Respuesta del registro con WSCoor 1.1</span><span class="sxs-lookup"><span data-stu-id="a5d25-239">Register Response with WSCoor 1.1</span></span>  
  
```xml  
<s:Envelope>  
<s:Header>   
<a:Action> http://docs.oasis-open.org/ws-tx/wscoor/2006/06/RegisterResponse  
</a:Action>   
<a:MessageID>urn:uuid:ed418b86-a75e-4aea-9d4e-a5d0cb5c088d</a:MessageID>  
<a:RelatesTo> urn:uuid:ed418b86-a75e-4aea-9d4e-a5d0cb5c088e </a:RelatesTo>  
<a:To>https://...</a:To>   
<wsse:Security   
s:mustUnderstand="1"   
xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"   
xmlns:wssu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">   
<wssu:Timestamp>   
<wssu:Created>2005-12-15T23:36:13.827Z</wssu:Created>  
<wssu:Expires>2005-12-15T23:41:13.827Z</wssu:Expires>  
</wssu:Timestamp>   
</wsse:Security>   
</s:Header>   
<s:Body xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">   
<wscoor:RegisterResponse>   
<wscoor:CoordinatorProtocolService>  
<a:Address>https://...</a:Address>  
<a:ReferenceParameters> ... </a:ReferenceParameters>  
</wscoor:CoordinatorProtocolService>   
</wscoor:RegisterResponse>   
</s:Body>   
</s:Envelope>  
```  
  
### <a name="two-phase-commit-protocol-messages"></a><span data-ttu-id="a5d25-240">Mensajes de protocolo de confirmación de dos fase</span><span class="sxs-lookup"><span data-stu-id="a5d25-240">Two Phase Commit Protocol Messages</span></span>  
 <span data-ttu-id="a5d25-241">El siguiente mensaje se relaciona con el protocolo de confirmación en dos fases (2PC).</span><span class="sxs-lookup"><span data-stu-id="a5d25-241">The following message relates to the two-phase commit (2PC) protocol.</span></span>  
  
#### <a name="commit-with-wsat-10"></a><span data-ttu-id="a5d25-242">Confirmación con WSAT 1,0</span><span class="sxs-lookup"><span data-stu-id="a5d25-242">Commit with WSAT 1.0</span></span>  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <a:Action>http://.../ws/2004/10/wsat/Commit</a:Action>  
    <a:To>https://...</a:To>  
    <wsse:Security   
      s:mustUnderstand="1"   
      xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"  
      xmlns:wssu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">  
      <wssu:Timestamp wssu:Id="_0" >  
        <wssu:Created>2005-12-15T23:36:13.827Z</wssu:Created>  
        <wssu:Expires>2005-12-15T23:41:13.827Z</wssu:Expires>  
      </wssu:Timestamp>  
   </wsse:Security>  
  </s:Header>  
  <s:Body xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">  
    <wsat:Commit />  
  </s:Body>  
</s:Envelope>  
```  
  
#### <a name="commit-with-wsat-11"></a><span data-ttu-id="a5d25-243">Confirmar con WSAT 1.1</span><span class="sxs-lookup"><span data-stu-id="a5d25-243">Commit with WSAT 1.1</span></span>  
  
```xml  
<s:Envelope>  
<s:Header>   
<a:Action>http://docs.oasis-open.org/ws-tx/wsat/2006/06</a:Action>  
<a:To>https://...</a:To>   
<wsse:Security   
s:mustUnderstand="1"   
xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"   
xmlns:wssu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">   
<wssu:Timestamp wssu:Id="_0" >   
<wssu:Created>2005-12-15T23:36:13.827Z</wssu:Created>  
<wssu:Expires>2005-12-15T23:41:13.827Z</wssu:Expires>  
</wssu:Timestamp>   
</wsse:Security>   
</s:Header>   
<s:Body xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">   
<wsat:Commit />   
</s:Body>   
</s:Envelope>  
```  
  
### <a name="application-messages"></a><span data-ttu-id="a5d25-244">Mensajes de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="a5d25-244">Application Messages</span></span>  
 <span data-ttu-id="a5d25-245">Los siguientes mensajes son mensajes de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="a5d25-245">The following messages are application messages.</span></span>  
  
#### <a name="application-message-request"></a><span data-ttu-id="a5d25-246">Solicitud de mensaje de aplicación</span><span class="sxs-lookup"><span data-stu-id="a5d25-246">Application message-Request</span></span>  
  
```xml  
<s:Envelope>  
  <s:Header>  
<!-- Addressing headers, all signed-->  
    <wsse:Security s:mustUnderstand="1">  
      <wssu:Timestamp wssu:Id="timestamp">   
        <wssu:Created>2005-10-25T06:29:18.703Z</wssu:Created>  
        <wssu:Expires>2005-10-25T06:34:18.703Z</wssu:Expires>  
      </wssu:Timestamp>  
      <wsse:BinarySecurityToken   
          wssu:Id="IA_Certificate"   
          ValueType="...#X509v3"   
          EncodingType="...#Base64Binary">  
        <!-- IA certificate -->  
      </wsse:BinarySecurityToken>  
      <e:EncryptedKey Id="encrypted_key">  
            <!-- ephemeral key encrypted for PA certificate -->    
        <e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#">  
          <e:DataReference URI="#encrypted_body"/>  
          <e:DataReference URI="#encrypted_CCi"/>  
          <e:DataReference URI="#encrypted_issuedtokens"/>  
        </e:ReferenceList>  
      </e:EncryptedKey>  
      <Signature xmlns="http://www.w3.org/2000/09/xmldsig#">  
        <!-- signature over Addressing headers, Timestamp, and Body -->  
      </Signature>  
    </wsse:Security>  
    <wsse11:EncryptedHeader >  
     <!-- encrypted wscoor:CoordinationContext header containing CCi -->  
    </wsse11:EncryptedHeader>  
    <wsse11:EncryptedHeader   
      <!-- encrypted wst:IssuedTokens header containing SCTi -->  
      <!-- wst:IssuedTokens header is taken verbatim from message #2 above, omitted for brevity -->  
    </wsse11:EncryptedHeader>  
  </s:Header>  
  <s:Body wssu:Id="body">  
    <!-- encrypted content of the Body element of the application message -->      
    <e:EncryptedData Id="encrypted_body"   
           Type="http://www.w3.org/2001/04/xmlenc#Content"   
           xmlns:e="http://www.w3.org/2001/04/xmlenc#">  
...  
    </e:EncryptedData>  
  </s:Body>  
</s:Envelope>  
```
