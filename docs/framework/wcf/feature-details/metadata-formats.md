---
title: Formatos de metadatos
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: baad1e68-28fc-4a6a-8a43-75e47e7fa871
caps.latest.revision: "12"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d250b57282d24780dcdd1e045f18d7528bd86a90
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="metadata-formats"></a><span data-ttu-id="b1105-102">Formatos de metadatos</span><span class="sxs-lookup"><span data-stu-id="b1105-102">Metadata Formats</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="b1105-103"> admite los formatos de metadatos que se encuentran en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="b1105-103"> supports the metadata formats in the following table.</span></span>  
  
## <a name="metadata-specifications-and-usage"></a><span data-ttu-id="b1105-104">Uso y especificaciones de los metadatos</span><span class="sxs-lookup"><span data-stu-id="b1105-104">Metadata Specifications and Usage</span></span>  
  
|<span data-ttu-id="b1105-105">Protocolo</span><span class="sxs-lookup"><span data-stu-id="b1105-105">Protocol</span></span>|<span data-ttu-id="b1105-106">Especificación y uso</span><span class="sxs-lookup"><span data-stu-id="b1105-106">Specification and usage</span></span>|  
|--------------|-----------------------------|  
|<span data-ttu-id="b1105-107">WSDL 1.1</span><span class="sxs-lookup"><span data-stu-id="b1105-107">WSDL 1.1</span></span>|[<span data-ttu-id="b1105-108">Lenguaje de descripción de servicios Web (WSDL) 1.1</span><span class="sxs-lookup"><span data-stu-id="b1105-108">Web Services Description Language (WSDL) 1.1</span></span>](http://go.microsoft.com/fwlink/?LinkId=94859)<br /><br /> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="b1105-109"> utiliza el lenguaje de descripción de servicios Web (WSDL) para describir servicios.</span><span class="sxs-lookup"><span data-stu-id="b1105-109"> uses Web Services Description Language (WSDL) to describe services.</span></span>|  
|<span data-ttu-id="b1105-110">esquema XML</span><span class="sxs-lookup"><span data-stu-id="b1105-110">XML Schema</span></span>|<span data-ttu-id="b1105-111">[XML Schema Part 2: Datatypes Second Edition](http://go.microsoft.com/fwlink/?LinkId=94861) y [esquema XML parte 1: estructuras, segunda edición](http://go.microsoft.com/fwlink/?LinkId=94862)</span><span class="sxs-lookup"><span data-stu-id="b1105-111">[XML Schema Part 2: Datatypes Second Edition](http://go.microsoft.com/fwlink/?LinkId=94861) and [XML Schema Part 1: Structures Second Edition](http://go.microsoft.com/fwlink/?LinkId=94862)</span></span><br /><br /> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="b1105-112"> utiliza el esquema XML para describir los tipos de datos utilizados en los mensajes.</span><span class="sxs-lookup"><span data-stu-id="b1105-112"> uses the XML Schema to describe data types used in messages.</span></span>|  
|<span data-ttu-id="b1105-113">Directiva WS</span><span class="sxs-lookup"><span data-stu-id="b1105-113">WS Policy</span></span>|[<span data-ttu-id="b1105-114">Directiva de servicios Web 1.2 - Framework (WS-Policy)</span><span class="sxs-lookup"><span data-stu-id="b1105-114">Web Services Policy 1.2 - Framework (WS-Policy)</span></span>](http://go.microsoft.com/fwlink/?LinkId=94864)<br /><br /> [<span data-ttu-id="b1105-115">Directiva de servicios Web 1.5 - Framework</span><span class="sxs-lookup"><span data-stu-id="b1105-115">Web Services Policy 1.5 - Framework</span></span>](http://go.microsoft.com/fwlink/?LinkId=94865)<br /><br /> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="b1105-116"> utiliza la especificación WS-Policy 1.2 ó 1.5 con las aserciones específicas del dominio para describir requisitos y funciones del servicio.</span><span class="sxs-lookup"><span data-stu-id="b1105-116"> uses the WS-Policy 1.2 or 1.5 specifications with domain-specific assertions to describe service requirements and capabilities.</span></span>|  
|<span data-ttu-id="b1105-117">Datos adjuntos de directivas WS</span><span class="sxs-lookup"><span data-stu-id="b1105-117">WS Policy Attachments</span></span>|[<span data-ttu-id="b1105-118">Directiva de servicios Web 1.2: datos adjuntos (WS-PolicyAttachment)</span><span class="sxs-lookup"><span data-stu-id="b1105-118">Web Services Policy 1.2 - Attachment (WS-PolicyAttachment)</span></span>](http://go.microsoft.com/fwlink/?LinkId=94866)<br /><br /> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="b1105-119"> implementa Datos adjuntos de directivas WS para adjuntar expresiones de directivas en varios ámbitos de WSDL.</span><span class="sxs-lookup"><span data-stu-id="b1105-119"> implements WS-Policy Attachments to attach policy expressions at various scopes in WSDL.</span></span>|  
|<span data-ttu-id="b1105-120">Intercambio de metadatos WS</span><span class="sxs-lookup"><span data-stu-id="b1105-120">WS Metadata Exchange</span></span>|[<span data-ttu-id="b1105-121">Intercambio de metadatos de servicios Web (WS-MetadataExchange) versión 1.1</span><span class="sxs-lookup"><span data-stu-id="b1105-121">Web Services Metadata Exchange (WS-MetadataExchange) version 1.1</span></span>](http://go.microsoft.com/fwlink/?LinkId=94868)<br /><br /> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="b1105-122"> implementa WS-MetadataExchange para recuperar el esquema XML, WSDL y WS-Policy.</span><span class="sxs-lookup"><span data-stu-id="b1105-122"> implements WS-MetadataExchange to retrieve XML Schema, WSDL, and WS-Policy.</span></span>|  
|<span data-ttu-id="b1105-123">Enlace de direccionamiento de WS para WSDL</span><span class="sxs-lookup"><span data-stu-id="b1105-123">WS Addressing Binding for WSDL</span></span>|[<span data-ttu-id="b1105-124">Web Services Addressing 1.0 - enlace WSDL</span><span class="sxs-lookup"><span data-stu-id="b1105-124">Web Services Addressing 1.0 - WSDL Binding</span></span>](http://go.microsoft.com/fwlink/?LinkId=94869)<br /><br /> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="b1105-125"> implementa WS-Addressing Binding para que WSDL adjunte información del direccionamiento en WSDL.</span><span class="sxs-lookup"><span data-stu-id="b1105-125"> implements WS-Addressing Binding for WSDL to attach addressing information in WSDL.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b1105-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="b1105-126">See Also</span></span>  
 [<span data-ttu-id="b1105-127">Protocolos admitidos por los enlaces de interoperabilidad proporcionados por el sistema de servicios Web</span><span class="sxs-lookup"><span data-stu-id="b1105-127">Web Services Protocols Supported by System-Provided Interoperability Bindings</span></span>](../../../../docs/framework/wcf/feature-details/web-services-protocols-supported-by-system-provided-interoperability-bindings.md)  
 [<span data-ttu-id="b1105-128">WSDL y directiva</span><span class="sxs-lookup"><span data-stu-id="b1105-128">WSDL and Policy</span></span>](../../../../docs/framework/wcf/feature-details/wsdl-and-policy.md)
