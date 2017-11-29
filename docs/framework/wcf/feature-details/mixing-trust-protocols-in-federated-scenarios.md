---
title: "Combinación de protocolos de confianza en escenarios federados"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d7b5fee9-2246-4b09-b8d7-9e63cb817279
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 007dec81766423ea2826e98ae0b6b399a1508f11
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="mixing-trust-protocols-in-federated-scenarios"></a><span data-ttu-id="78317-102">Combinación de protocolos de confianza en escenarios federados</span><span class="sxs-lookup"><span data-stu-id="78317-102">Mixing Trust Protocols in Federated Scenarios</span></span>
<span data-ttu-id="78317-103">Puede haber situaciones en las que los clientes federados se comuniquen con un servicio y un servicio de tokens de seguridad (STS) que no tengan la misma versión de confianza.</span><span class="sxs-lookup"><span data-stu-id="78317-103">There may be scenarios in which federated clients communicate with a service and a Security Token Service (STS) that do not have the same trust version.</span></span> <span data-ttu-id="78317-104">El WSDL del servicio puede contener una aserción `RequestSecurityTokenTemplate` con elementos WS-Trust que sean de versiones diferentes que las de STS.</span><span class="sxs-lookup"><span data-stu-id="78317-104">The service WSDL can contain a `RequestSecurityTokenTemplate` assertion with WS-Trust elements that are of different versions than the STS.</span></span> <span data-ttu-id="78317-105">En estos casos, un cliente de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] convierte los elementos de WS-Trust recibidos de `RequestSecurityTokenTemplate` para que coincida con la versión de confianza del STS.</span><span class="sxs-lookup"><span data-stu-id="78317-105">In such cases, a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] client converts the WS-Trust elements received from the `RequestSecurityTokenTemplate` to match the STS trust version.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="78317-106"> controla las versiones de confianza no coincidentes solo para los enlaces estándar.</span><span class="sxs-lookup"><span data-stu-id="78317-106"> handles mismatched trust versions only for standard bindings.</span></span> <span data-ttu-id="78317-107">Todos los parámetros de algoritmos estándar que son reconocidos por [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] forman parte del enlace estándar.</span><span class="sxs-lookup"><span data-stu-id="78317-107">All standard algorithm parameters that are recognized by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] are part of the standard binding.</span></span> <span data-ttu-id="78317-108">En este tema se describe el comportamiento de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] con distintas configuraciones de confianza entre el servicio y STS.</span><span class="sxs-lookup"><span data-stu-id="78317-108">This topic describes the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] behavior with various trust settings between the service and the STS.</span></span>  
  
## <a name="rp-feb-2005-and-sts-feb-2005"></a><span data-ttu-id="78317-109">RP Feb 2005 y STS Feb 2005</span><span class="sxs-lookup"><span data-stu-id="78317-109">RP Feb 2005 and STS Feb 2005</span></span>  
 <span data-ttu-id="78317-110">El WSDL de Usuario de confianza (RP) contiene los elementos siguientes en la sección `RequestSecurityTokenTemplate`:</span><span class="sxs-lookup"><span data-stu-id="78317-110">The WSDL for Relying Party (RP) contains the following elements within the `RequestSecurityTokenTemplate` section:</span></span>  
  
-   `CanonicalizationAlgorithm`  
  
-   `EncryptionAlgorithm`  
  
-   `EncryptWith`  
  
-   `SignWith`  
  
-   `KeySize`  
  
-   `KeyType`  
  
 <span data-ttu-id="78317-111">El archivo de configuración del cliente contiene una lista de parámetros.</span><span class="sxs-lookup"><span data-stu-id="78317-111">The client configuration file contains a list of parameters.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="78317-112"> no pueden diferenciar entre los parámetros del servicio y del cliente; agrega todos los parámetros y los envía en `RequestSecurityTokenTemplate` (RST).</span><span class="sxs-lookup"><span data-stu-id="78317-112"> cannot differentiate between the client and service parameters; it adds all the parameters and sends them in the `RequestSecurityTokenTemplate` (RST).</span></span>  
  
## <a name="rp-trust-13-and-sts-trust-13"></a><span data-ttu-id="78317-113">RP Trust 1.3 y STS Trust 1.3</span><span class="sxs-lookup"><span data-stu-id="78317-113">RP Trust 1.3 and STS Trust 1.3</span></span>  
 <span data-ttu-id="78317-114">El WSDL de RP contiene los elementos siguientes en la sección `RequestSecurityTokenTemplate`:</span><span class="sxs-lookup"><span data-stu-id="78317-114">The WSDL for RP contains the following elements within the `RequestSecurityTokenTemplate` section:</span></span>  
  
-   `CanonicalizationAlgorithm`  
  
-   `EncryptionAlgorithm`  
  
-   `EncryptWith`  
  
-   `SignWith`  
  
-   `KeySize`  
  
-   `KeyType`  
  
-   `KeyWrapAlgorithm`  
  
 <span data-ttu-id="78317-115">El archivo de configuración del cliente tiene un elemento `secondaryParameters` que contiene los parámetros especificados por RP.</span><span class="sxs-lookup"><span data-stu-id="78317-115">The client configuration file contains a `secondaryParameters` element that wraps the parameters specified by the RP.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="78317-116"> quita los elementos `EncryptionAlgorithm`, `CanonicalizationAlgorithm` y `KeyWrapAlgorithm` del elemento de nivel superior bajo el RST si están presentes dentro del elemento `SecondaryParameters`.</span><span class="sxs-lookup"><span data-stu-id="78317-116"> removes the `EncryptionAlgorithm`, `CanonicalizationAlgorithm` and `KeyWrapAlgorithm` elements from the top-level element under the RST if these are present inside the `SecondaryParameters` element.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="78317-117"> anexa el elemento `SecondaryParameters` al RST de salida sin modificar.</span><span class="sxs-lookup"><span data-stu-id="78317-117"> appends the `SecondaryParameters` element to the outgoing RST unmodified.</span></span>  
  
## <a name="rp-trust-feb-2005-and-sts-trust-13"></a><span data-ttu-id="78317-118">RP Trust Feb 2005 y STS Trust 1.3</span><span class="sxs-lookup"><span data-stu-id="78317-118">RP Trust Feb 2005 and STS Trust 1.3</span></span>  
 <span data-ttu-id="78317-119">El WSDL de RP contiene los elementos siguientes en la sección `RequestSecurityTokenTemplate`:</span><span class="sxs-lookup"><span data-stu-id="78317-119">The WSDL for RP contains the following elements in the `RequestSecurityTokenTemplate` section:</span></span>  
  
-   `CanonicalizationAlgorithm`  
  
-   `EncryptionAlgorithm`  
  
-   `EncryptWith`  
  
-   `SignWith`  
  
-   `KeySize`  
  
-   `KeyType`  
  
 <span data-ttu-id="78317-120">El archivo de configuración del cliente contiene una lista de parámetros.</span><span class="sxs-lookup"><span data-stu-id="78317-120">The client configuration file contains a list of parameters.</span></span>  
  
 <span data-ttu-id="78317-121">A partir del archivo de configuración del cliente, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no pueden diferenciar entre los parámetros del cliente y del servicio.</span><span class="sxs-lookup"><span data-stu-id="78317-121">From the client configuration file, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] cannot differentiate between the service and client parameters.</span></span> <span data-ttu-id="78317-122">Por consiguiente, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] convierte todos los parámetros a un espacio de nombres de la versión Trust 1.3.</span><span class="sxs-lookup"><span data-stu-id="78317-122">Therefore [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] converts all the parameters to a Trust version 1.3 namespace.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="78317-123"> controla los elementos `KeyType`, `KeySize` y `TokenType` de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="78317-123"> handles the `KeyType`, `KeySize`, and `TokenType` elements as follows:</span></span>  
  
-   <span data-ttu-id="78317-124">Descargue el WSDL, cree el enlace y asigne `KeyType`, `KeySize` y `TokenType` de los parámetros RP.</span><span class="sxs-lookup"><span data-stu-id="78317-124">Download the WSDL, create the binding, and assign `KeyType`, `KeySize`, and `TokenType` from the RP parameters.</span></span> <span data-ttu-id="78317-125">A continuación se genera el archivo de configuración del cliente.</span><span class="sxs-lookup"><span data-stu-id="78317-125">The client configuration file is then generated.</span></span>  
  
-   <span data-ttu-id="78317-126">Ahora, el cliente puede cambiar cualquier parámetro del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="78317-126">The client can now change any parameter in the configuration file.</span></span>  
  
-   <span data-ttu-id="78317-127">Durante el tiempo de ejecución, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] copia todos los parámetros especificados en la sección `AdditionalTokenParameters` del archivo de configuración del cliente excepto `KeyType`, `KeySize` y `TokenType`, porque estos parámetros se tienen en cuenta durante la generación del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="78317-127">During runtime, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] copies all parameters specified into the `AdditionalTokenParameters` section of the client configuration file except `KeyType`, `KeySize` and `TokenType`, because these parameters are accounted for during the configuration file generation.</span></span>  
  
## <a name="rp-trust-13-and-sts-trust-feb-2005"></a><span data-ttu-id="78317-128">RP Trust 1.3 y STS Trust Feb 2005</span><span class="sxs-lookup"><span data-stu-id="78317-128">RP Trust 1.3 and STS Trust Feb 2005</span></span>  
 <span data-ttu-id="78317-129">El WSDL de RP contiene los elementos siguientes en la sección `RequestSecurityTokenTemplate`:</span><span class="sxs-lookup"><span data-stu-id="78317-129">The WSDL for RP contains the following elements in the `RequestSecurityTokenTemplate` section:</span></span>  
  
-   `CanonicalizationAlgorithm`  
  
-   `EncryptionAlgorithm`  
  
-   `EncryptWith`  
  
-   `SignWith`  
  
-   `KeySize`  
  
-   `KeyType`  
  
-   `KeyWrapAlgorithm`  
  
 <span data-ttu-id="78317-130">El archivo de configuración del cliente tiene un elemento `secondaryParamters` que contiene los parámetros especificados por RP.</span><span class="sxs-lookup"><span data-stu-id="78317-130">The client configuration file contains a `secondaryParamters` element that wraps the parameters specified by the RP.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="78317-131"> copia todos los parámetros especificados dentro de la sección `SecondaryParameters` en el elemento RST de nivel superior, pero no los convierte al espacio de nombres WS-Trust de 2005.</span><span class="sxs-lookup"><span data-stu-id="78317-131"> copies all the parameters specified within the `SecondaryParameters` section to the top-level RST element, but does not convert them to the 2005 WS-Trust namespace.</span></span>
