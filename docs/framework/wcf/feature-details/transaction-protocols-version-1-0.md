---
title: Protocolos de transacción versión 1.0
ms.date: 03/30/2017
ms.assetid: 034679af-0002-402e-98a8-ef73dcd71bb6
ms.openlocfilehash: 9e21da0dfdda514e60b6f53090f5225b57aa1b75
ms.sourcegitcommit: fe8877e564deb68d77fa4b79f55584ac8d7e8997
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2020
ms.locfileid: "90720379"
---
# <a name="transaction-protocols-version-10"></a><span data-ttu-id="679e5-102">Protocolos de transacción versión 1.0</span><span class="sxs-lookup"><span data-stu-id="679e5-102">Transaction Protocols version 1.0</span></span>
<span data-ttu-id="679e5-103">Windows Communication Foundation (WCF) versión 1 implementa la versión 1,0 de los protocolos WS-Atomic Transaction y WS-Coordination.</span><span class="sxs-lookup"><span data-stu-id="679e5-103">Windows Communication Foundation (WCF) version 1 implements version 1.0 of the WS-Atomic Transaction and WS-Coordination protocols.</span></span> <span data-ttu-id="679e5-104">Para obtener más información acerca de la versión 1,1, consulte [protocolos de transacción](transaction-protocols.md).</span><span class="sxs-lookup"><span data-stu-id="679e5-104">For more information about version 1.1, see [Transaction Protocols](transaction-protocols.md).</span></span>  
  
|<span data-ttu-id="679e5-105">Especificación/documento</span><span class="sxs-lookup"><span data-stu-id="679e5-105">Specification/Document</span></span>|<span data-ttu-id="679e5-106">Link</span><span class="sxs-lookup"><span data-stu-id="679e5-106">Link</span></span>|  
|-----------------------------|----------|  
|<span data-ttu-id="679e5-107">WS-Coordination</span><span class="sxs-lookup"><span data-stu-id="679e5-107">WS-Coordination</span></span>|<http://specs.xmlsoap.org/ws/2004/10/wscoor/wscoor.pdf>|  
|<span data-ttu-id="679e5-108">Transacción WS-Atomic</span><span class="sxs-lookup"><span data-stu-id="679e5-108">WS-AtomicTransaction</span></span>|<http://specs.xmlsoap.org/ws/2004/10/wsat/wsat.pdf>|  
  
 <span data-ttu-id="679e5-109">La interoperabilidad en estas especificaciones de protocolo se requiere en dos niveles: entre las aplicaciones y entre los administradores de transacciones (véase la siguiente figura).</span><span class="sxs-lookup"><span data-stu-id="679e5-109">Interoperability on these protocol specifications is required at two levels: between applications and between transaction managers (see the following figure).</span></span> <span data-ttu-id="679e5-110">Las especificaciones describen en gran detalle los formatos de mensajes y el intercambio de mensajes para ambos niveles de interoperabilidad.</span><span class="sxs-lookup"><span data-stu-id="679e5-110">Specifications describe in great detail the message formats and message exchange for both interoperability levels.</span></span> <span data-ttu-id="679e5-111">Cierta seguridad, fiabilidad y codificaciones para el intercambio de aplicación a aplicación se aplican tal y como lo hacen para el intercambio normal de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="679e5-111">Certain security, reliability, and encodings for application-to-application exchange apply as they do for regular application exchange.</span></span> <span data-ttu-id="679e5-112">Sin embargo, para una interoperabilidad correcta entre los administradores de transacciones es necesario el acuerdo en el enlace determinado, porque el usuario no lo configura por regla general.</span><span class="sxs-lookup"><span data-stu-id="679e5-112">However, successful interoperability between transaction managers requires agreement on the particular binding, because it is usually not configured by the user.</span></span>  
  
 <span data-ttu-id="679e5-113">Este tema describe una composición de la especificación de transacción WS-Atomic (WS-AT) con seguridad y describe el enlace seguro utilizado para la comunicación entre administradores de transacciones.</span><span class="sxs-lookup"><span data-stu-id="679e5-113">This topic describes a composition of the WS-Atomic Transaction (WS-AT) specification with security and describes the secure binding used for communication between transaction managers.</span></span> <span data-ttu-id="679e5-114">El enfoque descrito en este documento se ha probado correctamente con otras implementaciones de WS-AT y WS-Coordination incluidos IBM, IONA, Sun Microsystems y otros.</span><span class="sxs-lookup"><span data-stu-id="679e5-114">The approach described in this document has been successfully tested with other implementations of WS-AT and WS-Coordination including IBM, IONA, Sun Microsystems, and others.</span></span>  
  
 <span data-ttu-id="679e5-115">En la ilustración siguiente se muestra la interoperabilidad entre dos administradores de transacciones, Transaction Manager 1 y Transaction Manager 2, y dos aplicaciones, Application 1 y Application 2:</span><span class="sxs-lookup"><span data-stu-id="679e5-115">The following figure depicts the interoperability between two transaction managers, Transaction Manager 1 and Transaction Manager 2, and two applications, Application 1 and Application 2:</span></span>  
  
 ![Captura de pantalla que muestra la interacción entre los administradores de transacciones.](./media/transaction-protocols/transaction-managers-flow.gif)  
  
 <span data-ttu-id="679e5-117">Considere un escenario típico WS-Coordination/transacciones WS-Atomic con un Iniciador (I) y un Participante (P).</span><span class="sxs-lookup"><span data-stu-id="679e5-117">Consider a typical WS-Coordination/WS-Atomic Transaction scenario with one Initiator (I) and one Participant (P).</span></span> <span data-ttu-id="679e5-118">Iniciador y Participante tienen administradores de transacciones (ITM y PTM, respectivamente).</span><span class="sxs-lookup"><span data-stu-id="679e5-118">Both Initiator and Participant have Transaction Managers, (ITM and PTM, respectively).</span></span> <span data-ttu-id="679e5-119">La confirmación en dos fases se conoce como 2PC en este tema.</span><span class="sxs-lookup"><span data-stu-id="679e5-119">Two-phase commit is referred to as 2PC in this topic.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="679e5-120">1. CreateCoordinationContext</span><span class="sxs-lookup"><span data-stu-id="679e5-120">1. CreateCoordinationContext</span></span>|<span data-ttu-id="679e5-121">12. respuesta del mensaje de aplicación</span><span class="sxs-lookup"><span data-stu-id="679e5-121">12. Application Message Response</span></span>|  
|<span data-ttu-id="679e5-122">2. CreateCoordinationContextResponse</span><span class="sxs-lookup"><span data-stu-id="679e5-122">2. CreateCoordinationContextResponse</span></span>|<span data-ttu-id="679e5-123">13. confirmación (finalización)</span><span class="sxs-lookup"><span data-stu-id="679e5-123">13. Commit (Completion)</span></span>|  
|<span data-ttu-id="679e5-124">3. registro (finalización)</span><span class="sxs-lookup"><span data-stu-id="679e5-124">3. Register (Completion)</span></span>|<span data-ttu-id="679e5-125">14. preparar (2PC)</span><span class="sxs-lookup"><span data-stu-id="679e5-125">14. Prepare (2PC)</span></span>|  
|<span data-ttu-id="679e5-126">4. RegisterResponse</span><span class="sxs-lookup"><span data-stu-id="679e5-126">4. RegisterResponse</span></span>|<span data-ttu-id="679e5-127">15. preparar (2PC)</span><span class="sxs-lookup"><span data-stu-id="679e5-127">15. Prepare (2PC)</span></span>|  
|<span data-ttu-id="679e5-128">5. mensaje de la aplicación</span><span class="sxs-lookup"><span data-stu-id="679e5-128">5. Application Message</span></span>|<span data-ttu-id="679e5-129">16. preparado (2PC)</span><span class="sxs-lookup"><span data-stu-id="679e5-129">16. Prepared (2PC)</span></span>|  
|<span data-ttu-id="679e5-130">6. CreateCoordinationContext con contexto</span><span class="sxs-lookup"><span data-stu-id="679e5-130">6. CreateCoordinationContext with Context</span></span>|<span data-ttu-id="679e5-131">17. preparado (2PC)</span><span class="sxs-lookup"><span data-stu-id="679e5-131">17. Prepared (2PC)</span></span>|  
|<span data-ttu-id="679e5-132">7. registro (duradero)</span><span class="sxs-lookup"><span data-stu-id="679e5-132">7. Register (Durable)</span></span>|<span data-ttu-id="679e5-133">18. confirmado (finalización)</span><span class="sxs-lookup"><span data-stu-id="679e5-133">18. Committed (Completion)</span></span>|  
|<span data-ttu-id="679e5-134">8. RegisterResponse</span><span class="sxs-lookup"><span data-stu-id="679e5-134">8. RegisterResponse</span></span>|<span data-ttu-id="679e5-135">19. Commit (2PC)</span><span class="sxs-lookup"><span data-stu-id="679e5-135">19. Commit (2PC)</span></span>|  
|<span data-ttu-id="679e5-136">9. CreateCoordinationContextResponse</span><span class="sxs-lookup"><span data-stu-id="679e5-136">9. CreateCoordinationContextResponse</span></span>|<span data-ttu-id="679e5-137">20. Commit (2PC)</span><span class="sxs-lookup"><span data-stu-id="679e5-137">20. Commit (2PC)</span></span>|  
|<span data-ttu-id="679e5-138">10. registro (duradero)</span><span class="sxs-lookup"><span data-stu-id="679e5-138">10. Register (Durable)</span></span>|<span data-ttu-id="679e5-139">21. confirmado (2PC)</span><span class="sxs-lookup"><span data-stu-id="679e5-139">21. Committed (2PC)</span></span>|  
|<span data-ttu-id="679e5-140">11. RegisterResponse</span><span class="sxs-lookup"><span data-stu-id="679e5-140">11. RegisterResponse</span></span>|<span data-ttu-id="679e5-141">22. confirmado (2PC)</span><span class="sxs-lookup"><span data-stu-id="679e5-141">22. Committed (2PC)</span></span>|  
  
 <span data-ttu-id="679e5-142">Este documento describe una composición de la especificación de transacción WS-Atomic con seguridad y describe el enlace seguro utilizado para la comunicación entre administradores de transacciones.</span><span class="sxs-lookup"><span data-stu-id="679e5-142">This document describes a composition of the WS-AtomicTransaction specification with security and describes the secure binding used for communication between transaction managers.</span></span> <span data-ttu-id="679e5-143">El enfoque descrito en este documento se ha probado correctamente con otras implementaciones de WS-AT y Coordinación del WS.</span><span class="sxs-lookup"><span data-stu-id="679e5-143">The approach described in this document has been successfully tested with other implementations of WS-AT and WS-Coordination.</span></span>  
  
 <span data-ttu-id="679e5-144">La figura y la tabla muestran cuatro clases de mensajes desde el punto de vista de la seguridad:</span><span class="sxs-lookup"><span data-stu-id="679e5-144">The figure and table illustrate four classes of messages from the viewpoint of security:</span></span>  
  
- <span data-ttu-id="679e5-145">Mensajes de activación (CreateCoordinationContext y CreateCoordinationContextResponse).</span><span class="sxs-lookup"><span data-stu-id="679e5-145">Activation messages (CreateCoordinationContext and CreateCoordinationContextResponse).</span></span>  
  
- <span data-ttu-id="679e5-146">Mensajes del registro (Register y RegisterResponse)</span><span class="sxs-lookup"><span data-stu-id="679e5-146">Registration messages (Register and RegisterResponse)</span></span>  
  
- <span data-ttu-id="679e5-147">Mensajes de protocolos (Preparar, Reversión, Confirmar, Anulado, etc.).</span><span class="sxs-lookup"><span data-stu-id="679e5-147">Protocol messages (Prepare, Rollback, Commit, Aborted, and so on).</span></span>  
  
- <span data-ttu-id="679e5-148">Mensajes de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="679e5-148">Application messages.</span></span>  
  
 <span data-ttu-id="679e5-149">Las primeras tres clases de mensajes están consideradas mensajes de Administrador de transacciones y su configuración de enlaces se describe en el "Intercambio de mensajes de aplicaciones" más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="679e5-149">The first three message classes are considered Transaction Manager messages and their binding configuration is described in the "Application Message Exchange" later in this topic.</span></span> <span data-ttu-id="679e5-150">La cuarta clase del mensaje son mensajes de aplicación a aplicación y se describe en la sección “Ejemplos de mensajes” más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="679e5-150">The fourth class of message is application to application messages and is described in the "Message Examples" section later in this topic.</span></span> <span data-ttu-id="679e5-151">En esta sección se describen los enlaces de protocolo usados por WCF para cada una de estas clases.</span><span class="sxs-lookup"><span data-stu-id="679e5-151">This section describes the protocol bindings used for each of these classes by WCF.</span></span>  
  
 <span data-ttu-id="679e5-152">Los siguientes espacios de nombres XML y prefijos asociados se utilizan a lo largo de este documento.</span><span class="sxs-lookup"><span data-stu-id="679e5-152">The following XML Namespaces and associated prefixes are used throughout this document.</span></span>  
  
|<span data-ttu-id="679e5-153">Prefijo</span><span class="sxs-lookup"><span data-stu-id="679e5-153">Prefix</span></span>|<span data-ttu-id="679e5-154">URI de espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="679e5-154">Namespace URI</span></span>|  
|------------|-------------------|  
|<span data-ttu-id="679e5-155">s11</span><span class="sxs-lookup"><span data-stu-id="679e5-155">s11</span></span>|`http://schemas.xmlsoap.org/soap/envelope`|  
|<span data-ttu-id="679e5-156">wsa</span><span class="sxs-lookup"><span data-stu-id="679e5-156">wsa</span></span>|`http://www.w3.org/2004/08/addressing`|  
|<span data-ttu-id="679e5-157">wscoor</span><span class="sxs-lookup"><span data-stu-id="679e5-157">wscoor</span></span>|`http://schemas.xmlsoap.org/ws/2004/10/wscoor`|  
|<span data-ttu-id="679e5-158">wsat</span><span class="sxs-lookup"><span data-stu-id="679e5-158">wsat</span></span>|`http://schemas.xmlsoap.org/ws/2004/10/wsat`|  
|<span data-ttu-id="679e5-159">t</span><span class="sxs-lookup"><span data-stu-id="679e5-159">t</span></span>|`http://schemas.xmlsoap.org/ws/2005/02/trust`|  
|<span data-ttu-id="679e5-160">o</span><span class="sxs-lookup"><span data-stu-id="679e5-160">o</span></span>|`http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd`|  
|<span data-ttu-id="679e5-161">xsd</span><span class="sxs-lookup"><span data-stu-id="679e5-161">xsd</span></span>|`http://www.w3.org/2001/XMLSchema`|  
  
## <a name="transaction-manager-bindings"></a><span data-ttu-id="679e5-162">Enlaces del administrador de transacciones</span><span class="sxs-lookup"><span data-stu-id="679e5-162">Transaction Manager Bindings</span></span>  
 <span data-ttu-id="679e5-163">R1001: los administradores de transacciones deben utilizar SOAP 1.1 y WS-Addressing 2004/08 para intercambios de mensajes de transacciones WS-Atomic y WS-Coordination.</span><span class="sxs-lookup"><span data-stu-id="679e5-163">R1001: Transaction Managers must use SOAP 1.1 and WS-Addressing 2004/08 for WS-Atomic Transaction and WS-Coordination message exchanges.</span></span>  
  
 <span data-ttu-id="679e5-164">Los mensajes de la aplicación no se restringen a estos enlaces y se describen más adelante.</span><span class="sxs-lookup"><span data-stu-id="679e5-164">Application messages are not constrained to these bindings and are described later.</span></span>  
  
### <a name="transaction-manager-https-binding"></a><span data-ttu-id="679e5-165">Enlace HTTPS de administrador de transacciones</span><span class="sxs-lookup"><span data-stu-id="679e5-165">Transaction Manager HTTPS Binding</span></span>  
 <span data-ttu-id="679e5-166">El enlace HTTPS del administrador de transacciones confía solamente en la seguridad de transporte para lograr la seguridad y establecer confianza entre cada par de remitente-receptor en el árbol de transacciones.</span><span class="sxs-lookup"><span data-stu-id="679e5-166">The transaction manager HTTPS binding relies solely on transport security to achieve security and establish trust between each sender-receiver pair in the transaction tree.</span></span>  
  
#### <a name="https-transport-configuration"></a><span data-ttu-id="679e5-167">Configuración de transporte HTTPS</span><span class="sxs-lookup"><span data-stu-id="679e5-167">HTTPS Transport Configuration</span></span>  
 <span data-ttu-id="679e5-168">Los certificados X.509 se utilizan para establecer la identidad del administrador de transacciones.</span><span class="sxs-lookup"><span data-stu-id="679e5-168">X.509 certificates are used to establish Transaction Manager Identity.</span></span> <span data-ttu-id="679e5-169">Se requiere la autenticación cliente/servidor, y la autorización cliente/servidor queda como un detalle de implementación:</span><span class="sxs-lookup"><span data-stu-id="679e5-169">Client/server authentication is required, and client/server authorization is left as an implementation detail:</span></span>  
  
- <span data-ttu-id="679e5-170">R1111: los certificados X.509 presentados a través de la conexión deben tener un nombre de sujeto que coincida con el nombre de dominio completo (FQDN) del equipo de origen.</span><span class="sxs-lookup"><span data-stu-id="679e5-170">R1111: X.509 certificates presented over the wire must have a subject name that matches the fully qualified domain name (FQDN) of the originating machine.</span></span>  
  
- <span data-ttu-id="679e5-171">B1112: DNS debe ser funcional entre cada par remitente-receptor del sistema para que las comprobaciones de nombre de sujeto X.509 se realicen correctamente.</span><span class="sxs-lookup"><span data-stu-id="679e5-171">B1112: DNS must be functional between each sender-receiver pair in the system for X.509 subject name checks to succeed.</span></span>  
  
#### <a name="activation-and-registration-binding-configuration"></a><span data-ttu-id="679e5-172">Activación y configuración de enlace de registro</span><span class="sxs-lookup"><span data-stu-id="679e5-172">Activation and Registration Binding Configuration</span></span>  
 <span data-ttu-id="679e5-173">WCF requiere un enlace dúplex de solicitud/respuesta con correlación sobre HTTPS.</span><span class="sxs-lookup"><span data-stu-id="679e5-173">WCF requires request/reply duplex binding with correlation over HTTPS.</span></span> <span data-ttu-id="679e5-174">(Para obtener más información sobre la correlación y descripciones de los patrones de intercambio de mensajes de solicitud/respuesta, vea Transacción WS-Atomic, sección 8.)</span><span class="sxs-lookup"><span data-stu-id="679e5-174">(For more information about correlation and descriptions of the request/reply message exchange patterns, see WS-Atomic Transaction, Section 8.)</span></span>  
  
#### <a name="2pc-protocol-binding-configuration"></a><span data-ttu-id="679e5-175">Configuración de enlace de protocolo 2PC</span><span class="sxs-lookup"><span data-stu-id="679e5-175">2PC Protocol Binding Configuration</span></span>  
 <span data-ttu-id="679e5-176">WCF admite mensajes unidireccionales (datagrama) a través de HTTPS.</span><span class="sxs-lookup"><span data-stu-id="679e5-176">WCF supports one-way (datagram) messages over HTTPS.</span></span> <span data-ttu-id="679e5-177">La correlación entre los mensajes queda como un detalle de implementación.</span><span class="sxs-lookup"><span data-stu-id="679e5-177">Correlation among the messages is left as an implementation detail.</span></span>  
  
 <span data-ttu-id="679e5-178">B2131: las implementaciones deben admitir `wsa:ReferenceParameters` tal y como se describe en WS-Addressing para lograr la correlación de los mensajes 2pc de WCF.</span><span class="sxs-lookup"><span data-stu-id="679e5-178">B2131: Implementations must support `wsa:ReferenceParameters` as described in WS-Addressing to achieve correlation of WCF’s 2PC messages.</span></span>  
  
### <a name="transaction-manager-mixed-security-binding"></a><span data-ttu-id="679e5-179">Enlace de seguridad mixta del administrador de transacciones</span><span class="sxs-lookup"><span data-stu-id="679e5-179">Transaction Manager Mixed Security Binding</span></span>  
 <span data-ttu-id="679e5-180">Se trata de un enlace alternativo (modo mixto) que usa la seguridad de transporte combinada con el modelo de token emitido por WS-Coordination para fines de establecimiento de identidades.</span><span class="sxs-lookup"><span data-stu-id="679e5-180">This is an alternate (mixed mode) binding that uses transport security combined with the  WS-Coordination Issued Token model for identity establishment purposes.</span></span>  <span data-ttu-id="679e5-181">La activación y el registro son los únicos elementos que difieren entre los dos enlaces.</span><span class="sxs-lookup"><span data-stu-id="679e5-181">Activation and Registration are the only elements that differ between the two bindings.</span></span>  
  
#### <a name="https-transport-configuration"></a><span data-ttu-id="679e5-182">Configuración de transporte HTTPS</span><span class="sxs-lookup"><span data-stu-id="679e5-182">HTTPS Transport Configuration</span></span>  
 <span data-ttu-id="679e5-183">Los certificados X.509 se utilizan para establecer la identidad del administrador de transacciones.</span><span class="sxs-lookup"><span data-stu-id="679e5-183">X.509 certificates are used to establish Transaction Manager Identity.</span></span> <span data-ttu-id="679e5-184">Se requiere la autenticación cliente/servidor, y la autorización cliente/servidor queda como un detalle de implementación.</span><span class="sxs-lookup"><span data-stu-id="679e5-184">Client/Server authentication is required, and client/server authorization is left as an implementation detail.</span></span>  
  
#### <a name="activation-message-binding-configuration"></a><span data-ttu-id="679e5-185">Configuración del enlace de mensajes de activación</span><span class="sxs-lookup"><span data-stu-id="679e5-185">Activation Message Binding Configuration</span></span>  
 <span data-ttu-id="679e5-186">Los mensajes de activación normalmente no participan en la interoperabilidad porque, por lo general, se producen entre una aplicación y su administrador de transacción local.</span><span class="sxs-lookup"><span data-stu-id="679e5-186">Activation Messages usually do not participate in interoperability because they typically occur between an application and its local Transaction Manager.</span></span>  
  
 <span data-ttu-id="679e5-187">B1221: WCF usa el enlace HTTPS dúplex (descrito en [protocolos de mensajería](messaging-protocols.md)) para los mensajes de activación.</span><span class="sxs-lookup"><span data-stu-id="679e5-187">B1221: WCF uses duplex HTTPS binding (described in [Messaging Protocols](messaging-protocols.md)) for Activation messages.</span></span> <span data-ttu-id="679e5-188">Los mensajes de solicitud y respuesta se ponen en correlación mediante WS-Addressing 2004/08.</span><span class="sxs-lookup"><span data-stu-id="679e5-188">Request and Reply messages are correlated using WS-Addressing 2004/08.</span></span>  
  
 <span data-ttu-id="679e5-189">La especificación de transacción WS-Atomic, sección 8, describe detalles adicionales sobre la correlación y los patrones de intercambio de mensajes.</span><span class="sxs-lookup"><span data-stu-id="679e5-189">WS-Atomic Transaction specification, Section 8, describes further details about correlation and the message exchange patterns.</span></span>  
  
- <span data-ttu-id="679e5-190">R1222: tras recibir `CreateCoordinationContext`, el coordinador debe emitir un `SecurityContextToken` con `STx`secreto asociado.</span><span class="sxs-lookup"><span data-stu-id="679e5-190">R1222: Upon receiving a `CreateCoordinationContext`, the Coordinator must issue a `SecurityContextToken` with associated secret `STx`.</span></span> <span data-ttu-id="679e5-191">Este token se devuelve dentro de un encabezado `t:IssuedTokens` que sigue la especificación de WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="679e5-191">This token is returned inside a `t:IssuedTokens` header following WS-Trust specification.</span></span>  
  
- <span data-ttu-id="679e5-192">R1223: si la activación se produce dentro de un contexto de coordinación existente, el encabezado `t:IssuedTokens` con el `SecurityContextToken` asociado al contexto existente debe fluir en el mensaje `CreateCoordinationContext`.</span><span class="sxs-lookup"><span data-stu-id="679e5-192">R1223: If Activation occurs within an existing Coordination Context, the `t:IssuedTokens` header with the `SecurityContextToken` associated with existing Context must flow on the `CreateCoordinationContext` message.</span></span>  
  
 <span data-ttu-id="679e5-193">`t:IssuedTokens`Se debe generar un nuevo encabezado para adjuntarlo al `wscoor:CreateCoordinationContextResponse` mensaje saliente.</span><span class="sxs-lookup"><span data-stu-id="679e5-193">A new `t:IssuedTokens` header should be generated for attaching to the outgoing `wscoor:CreateCoordinationContextResponse` message.</span></span>  
  
#### <a name="registration-message-binding-configuration"></a><span data-ttu-id="679e5-194">Configuración del enlace de mensajes de registro</span><span class="sxs-lookup"><span data-stu-id="679e5-194">Registration Message Binding Configuration</span></span>  
 <span data-ttu-id="679e5-195">B1231: WCF usa el enlace HTTPS dúplex (descrito en [protocolos de mensajería](messaging-protocols.md)).</span><span class="sxs-lookup"><span data-stu-id="679e5-195">B1231: WCF uses duplex HTTPS binding (described in [Messaging Protocols](messaging-protocols.md)).</span></span> <span data-ttu-id="679e5-196">Los mensajes de solicitud y respuesta se ponen en correlación mediante WS-Addressing 2004/08.</span><span class="sxs-lookup"><span data-stu-id="679e5-196">Request and Reply messages are correlated using WS-Addressing 2004/08.</span></span>  
  
 <span data-ttu-id="679e5-197">La transacción WS-Atomic, sección 8, describe detalles adicionales sobre la correlación y las descripciones del patrón de intercambio de mensajes.</span><span class="sxs-lookup"><span data-stu-id="679e5-197">WS-AtomicTransaction, Section 8, describes further details about correlation and descriptions of the message exchange patterns.</span></span>  
  
 <span data-ttu-id="679e5-198">R1232: `wscoor:Register` los mensajes salientes deben usar el `IssuedTokenOverTransport` modo de autenticación descrito en [protocolos de seguridad](security-protocols.md).</span><span class="sxs-lookup"><span data-stu-id="679e5-198">R1232: Outgoing `wscoor:Register` messages must use the `IssuedTokenOverTransport` authentication mode described in [Security Protocols](security-protocols.md).</span></span>  
  
 <span data-ttu-id="679e5-199">El `wsse:Timestamp` elemento debe estar firmado utilizando el `SecurityContextToken STx` emitido.</span><span class="sxs-lookup"><span data-stu-id="679e5-199">The `wsse:Timestamp` element must be signed using the `SecurityContextToken STx` issued.</span></span> <span data-ttu-id="679e5-200">Esta firma es una prueba de posesión del token asociado a la transacción determinada y se utiliza para autenticar a un participante enumerado en la transacción.</span><span class="sxs-lookup"><span data-stu-id="679e5-200">This signature is a proof of possession of the token associated with particular transaction and is used to authenticate a participant enlisting in the transaction.</span></span> <span data-ttu-id="679e5-201">El mensaje RegistrationResponse se devuelve sobre HTTPS.</span><span class="sxs-lookup"><span data-stu-id="679e5-201">The RegistrationResponse message is sent back over HTTPS.</span></span>  
  
#### <a name="2pc-protocol-binding-configuration"></a><span data-ttu-id="679e5-202">Configuración de enlace de protocolo 2PC</span><span class="sxs-lookup"><span data-stu-id="679e5-202">2PC Protocol Binding Configuration</span></span>  
 <span data-ttu-id="679e5-203">WCF admite mensajes unidireccionales (datagrama) a través de HTTPS.</span><span class="sxs-lookup"><span data-stu-id="679e5-203">WCF supports one-way (datagram) messages over HTTPS.</span></span> <span data-ttu-id="679e5-204">La correlación entre los mensajes queda como un detalle de implementación.</span><span class="sxs-lookup"><span data-stu-id="679e5-204">Correlation among the messages is left as an implementation detail.</span></span>  
  
 <span data-ttu-id="679e5-205">B2131: las implementaciones deben admitir `wsa:ReferenceParameters` tal y como se describe en WS-Addressing para lograr la correlación de los mensajes 2pc de WCF.</span><span class="sxs-lookup"><span data-stu-id="679e5-205">B2131: Implementations must support `wsa:ReferenceParameters` as described in WS-Addressing to achieve correlation of WCF’s 2PC messages.</span></span>  
  
## <a name="application-message-exchange"></a><span data-ttu-id="679e5-206">Intercambio de mensajes de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="679e5-206">Application Message Exchange</span></span>  
 <span data-ttu-id="679e5-207">Las aplicaciones pueden utilizar cualquier enlace determinado para los mensajes de aplicación a aplicación, con tal de que el enlace cumpla los siguientes requisitos de seguridad:</span><span class="sxs-lookup"><span data-stu-id="679e5-207">Applications are free to use any particular binding for application-to-application messages, as long as the binding meets the following security requirements:</span></span>  
  
- <span data-ttu-id="679e5-208">R2001: los mensajes de aplicación a aplicación deben fluir el encabezado `t:IssuedTokens` junto con `CoordinationContext` en el encabezado del mensaje.</span><span class="sxs-lookup"><span data-stu-id="679e5-208">R2001: Application-to-application messages must flow the `t:IssuedTokens` header along with the `CoordinationContext` in the header of the message.</span></span>  
  
- <span data-ttu-id="679e5-209">R2002: se debe proporcionar la integridad y confidencialidad de `t:IssuedToken`.</span><span class="sxs-lookup"><span data-stu-id="679e5-209">R2002: Integrity and confidentiality of `t:IssuedToken` must be provided.</span></span>  
  
 <span data-ttu-id="679e5-210">El encabezado `CoordinationContext` contiene `wscoor:Identifier`.</span><span class="sxs-lookup"><span data-stu-id="679e5-210">The `CoordinationContext` header contains `wscoor:Identifier`.</span></span> <span data-ttu-id="679e5-211">Aunque la definición de `xsd:AnyURI` permite el uso de identificadores URI absolutos y relativos, WCF solo admite `wscoor:Identifiers` , que son URI absolutos.</span><span class="sxs-lookup"><span data-stu-id="679e5-211">While the definition of `xsd:AnyURI` allows the use of both absolute and relative URIs, WCF supports only `wscoor:Identifiers`, which are absolute URIs.</span></span>  
  
 <span data-ttu-id="679e5-212">Si el `wscoor:Identifier` de `wscoor:CoordinationContext` es un URI relativo, los errores se devolverán desde los servicios de WCF transaccionales.</span><span class="sxs-lookup"><span data-stu-id="679e5-212">If the `wscoor:Identifier` of the `wscoor:CoordinationContext` is a relative URI, faults will be returned from transactional WCF services.</span></span>  
  
## <a name="message-examples"></a><span data-ttu-id="679e5-213">Ejemplos de mensajes</span><span class="sxs-lookup"><span data-stu-id="679e5-213">Message Examples</span></span>  
  
### <a name="createcoordinationcontext-requestresponse-messages"></a><span data-ttu-id="679e5-214">Mensajes de solicitud/respuesta CreateCoordinationContext</span><span class="sxs-lookup"><span data-stu-id="679e5-214">CreateCoordinationContext Request/Response Messages</span></span>  
 <span data-ttu-id="679e5-215">Los siguientes mensajes siguen un patrón de solicitud/respuesta.</span><span class="sxs-lookup"><span data-stu-id="679e5-215">The following messages follow a request/response pattern.</span></span>  
  
#### <a name="createcoordinationcontext"></a><span data-ttu-id="679e5-216">CreateCoordinationContext</span><span class="sxs-lookup"><span data-stu-id="679e5-216">CreateCoordinationContext</span></span>  
  
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
        <wsu:Created>2005-12-15T23:36:09.921Z</wsu:Created>  
        <wsu:Expires>2005-12-15T23:41:09.921Z</wsu:Expires>  
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
  
#### <a name="createcoordinationcontextresponse"></a><span data-ttu-id="679e5-217">CreateCoordinationContextResponse</span><span class="sxs-lookup"><span data-stu-id="679e5-217">CreateCoordinationContextResponse</span></span>  
  
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
  
### <a name="registration-messages"></a><span data-ttu-id="679e5-218">Mensajes del registro</span><span class="sxs-lookup"><span data-stu-id="679e5-218">Registration Messages</span></span>  
 <span data-ttu-id="679e5-219">Los siguientes mensajes son mensajes del registro.</span><span class="sxs-lookup"><span data-stu-id="679e5-219">The following messages are registration messages.</span></span>  
  
#### <a name="register"></a><span data-ttu-id="679e5-220">Registrarse</span><span class="sxs-lookup"><span data-stu-id="679e5-220">Register</span></span>  
  
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
  
#### <a name="register-response"></a><span data-ttu-id="679e5-221">Respuesta de registro</span><span class="sxs-lookup"><span data-stu-id="679e5-221">Register Response</span></span>  
  
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
  
### <a name="two-phase-commit-protocol-messages"></a><span data-ttu-id="679e5-222">Mensajes de protocolo de confirmación de dos fase</span><span class="sxs-lookup"><span data-stu-id="679e5-222">Two Phase Commit Protocol Messages</span></span>  
 <span data-ttu-id="679e5-223">El siguiente mensaje se relaciona con el protocolo de confirmación en dos fases (2PC).</span><span class="sxs-lookup"><span data-stu-id="679e5-223">The following message relates to the two-phase commit (2PC) protocol.</span></span>  
  
#### <a name="commit"></a><span data-ttu-id="679e5-224">Commit</span><span class="sxs-lookup"><span data-stu-id="679e5-224">Commit</span></span>  
  
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
  
### <a name="application-messages"></a><span data-ttu-id="679e5-225">Mensajes de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="679e5-225">Application Messages</span></span>  
 <span data-ttu-id="679e5-226">Los siguientes mensajes son mensajes de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="679e5-226">The following messages are application messages.</span></span>  
  
#### <a name="application-message-request"></a><span data-ttu-id="679e5-227">Solicitud de mensaje de aplicación</span><span class="sxs-lookup"><span data-stu-id="679e5-227">Application message-Request</span></span>  
  
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
    <wsse11:EncryptedHeader>  
     <!-- encrypted wscoor:CoordinationContext header containing CCi -->  
    </wsse11:EncryptedHeader>  
    <wsse11:EncryptedHeader>
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
