---
description: Más información acerca de cómo combinar protocolos de confianza en escenarios federados
title: Combinación de protocolos de confianza en escenarios federados
ms.date: 03/30/2017
ms.assetid: d7b5fee9-2246-4b09-b8d7-9e63cb817279
ms.openlocfilehash: f882b3728ed791f611a9f71f32840e68d8e17a1d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99733728"
---
# <a name="mixing-trust-protocols-in-federated-scenarios"></a><span data-ttu-id="91c05-103">Combinación de protocolos de confianza en escenarios federados</span><span class="sxs-lookup"><span data-stu-id="91c05-103">Mixing Trust Protocols in Federated Scenarios</span></span>

<span data-ttu-id="91c05-104">Puede haber situaciones en las que los clientes federados se comuniquen con un servicio y un servicio de tokens de seguridad (STS) que no tengan la misma versión de confianza.</span><span class="sxs-lookup"><span data-stu-id="91c05-104">There may be scenarios in which federated clients communicate with a service and a Security Token Service (STS) that do not have the same trust version.</span></span> <span data-ttu-id="91c05-105">El WSDL del servicio puede contener una aserción `RequestSecurityTokenTemplate` con elementos WS-Trust que sean de versiones diferentes que las de STS.</span><span class="sxs-lookup"><span data-stu-id="91c05-105">The service WSDL can contain a `RequestSecurityTokenTemplate` assertion with WS-Trust elements that are of different versions than the STS.</span></span> <span data-ttu-id="91c05-106">En tales casos, un cliente de Windows Communication Foundation (WCF) convierte los elementos WS-Trust recibidos de `RequestSecurityTokenTemplate` para que coincidan con la versión de confianza de STS.</span><span class="sxs-lookup"><span data-stu-id="91c05-106">In such cases, a Windows Communication Foundation (WCF) client converts the WS-Trust elements received from the `RequestSecurityTokenTemplate` to match the STS trust version.</span></span> <span data-ttu-id="91c05-107">WCF controla las versiones de confianza no coincidentes solo para los enlaces estándar.</span><span class="sxs-lookup"><span data-stu-id="91c05-107">WCF handles mismatched trust versions only for standard bindings.</span></span> <span data-ttu-id="91c05-108">Todos los parámetros de algoritmo estándar reconocidos por WCF forman parte del enlace estándar.</span><span class="sxs-lookup"><span data-stu-id="91c05-108">All standard algorithm parameters that are recognized by WCF are part of the standard binding.</span></span> <span data-ttu-id="91c05-109">En este tema se describe el comportamiento de WCF con varias configuraciones de confianza entre el servicio y el STS.</span><span class="sxs-lookup"><span data-stu-id="91c05-109">This topic describes the WCF behavior with various trust settings between the service and the STS.</span></span>  
  
## <a name="rp-feb-2005-and-sts-feb-2005"></a><span data-ttu-id="91c05-110">RP Feb 2005 y STS Feb 2005</span><span class="sxs-lookup"><span data-stu-id="91c05-110">RP Feb 2005 and STS Feb 2005</span></span>  

 <span data-ttu-id="91c05-111">El WSDL de Usuario de confianza (RP) contiene los elementos siguientes en la sección `RequestSecurityTokenTemplate`:</span><span class="sxs-lookup"><span data-stu-id="91c05-111">The WSDL for Relying Party (RP) contains the following elements within the `RequestSecurityTokenTemplate` section:</span></span>  
  
- `CanonicalizationAlgorithm`  
  
- `EncryptionAlgorithm`  
  
- `EncryptWith`  
  
- `SignWith`  
  
- `KeySize`  
  
- `KeyType`  
  
 <span data-ttu-id="91c05-112">El archivo de configuración del cliente contiene una lista de parámetros.</span><span class="sxs-lookup"><span data-stu-id="91c05-112">The client configuration file contains a list of parameters.</span></span>  
  
 <span data-ttu-id="91c05-113">WCF no puede diferenciar entre los parámetros de cliente y de servicio; agrega todos los parámetros y los envía en el `RequestSecurityTokenTemplate` (RST).</span><span class="sxs-lookup"><span data-stu-id="91c05-113">WCF cannot differentiate between the client and service parameters; it adds all the parameters and sends them in the `RequestSecurityTokenTemplate` (RST).</span></span>  
  
## <a name="rp-trust-13-and-sts-trust-13"></a><span data-ttu-id="91c05-114">RP Trust 1.3 y STS Trust 1.3</span><span class="sxs-lookup"><span data-stu-id="91c05-114">RP Trust 1.3 and STS Trust 1.3</span></span>  

 <span data-ttu-id="91c05-115">El WSDL de RP contiene los elementos siguientes en la sección `RequestSecurityTokenTemplate`:</span><span class="sxs-lookup"><span data-stu-id="91c05-115">The WSDL for RP contains the following elements within the `RequestSecurityTokenTemplate` section:</span></span>  
  
- `CanonicalizationAlgorithm`  
  
- `EncryptionAlgorithm`  
  
- `EncryptWith`  
  
- `SignWith`  
  
- `KeySize`  
  
- `KeyType`  
  
- `KeyWrapAlgorithm`  
  
 <span data-ttu-id="91c05-116">El archivo de configuración del cliente tiene un elemento `secondaryParameters` que contiene los parámetros especificados por RP.</span><span class="sxs-lookup"><span data-stu-id="91c05-116">The client configuration file contains a `secondaryParameters` element that wraps the parameters specified by the RP.</span></span>  
  
 <span data-ttu-id="91c05-117">WCF quita los `EncryptionAlgorithm` `CanonicalizationAlgorithm` elementos, y `KeyWrapAlgorithm` del elemento de nivel superior bajo el RST si están presentes dentro del `SecondaryParameters` elemento.</span><span class="sxs-lookup"><span data-stu-id="91c05-117">WCF removes the `EncryptionAlgorithm`, `CanonicalizationAlgorithm` and `KeyWrapAlgorithm` elements from the top-level element under the RST if these are present inside the `SecondaryParameters` element.</span></span> <span data-ttu-id="91c05-118">WCF anexa el `SecondaryParameters` elemento al RST de salida sin modificar.</span><span class="sxs-lookup"><span data-stu-id="91c05-118">WCF appends the `SecondaryParameters` element to the outgoing RST unmodified.</span></span>  
  
## <a name="rp-trust-feb-2005-and-sts-trust-13"></a><span data-ttu-id="91c05-119">RP Trust Feb 2005 y STS Trust 1.3</span><span class="sxs-lookup"><span data-stu-id="91c05-119">RP Trust Feb 2005 and STS Trust 1.3</span></span>  

 <span data-ttu-id="91c05-120">El WSDL de RP contiene los elementos siguientes en la sección `RequestSecurityTokenTemplate`:</span><span class="sxs-lookup"><span data-stu-id="91c05-120">The WSDL for RP contains the following elements in the `RequestSecurityTokenTemplate` section:</span></span>  
  
- `CanonicalizationAlgorithm`  
  
- `EncryptionAlgorithm`  
  
- `EncryptWith`  
  
- `SignWith`  
  
- `KeySize`  
  
- `KeyType`  
  
 <span data-ttu-id="91c05-121">El archivo de configuración del cliente contiene una lista de parámetros.</span><span class="sxs-lookup"><span data-stu-id="91c05-121">The client configuration file contains a list of parameters.</span></span>  
  
 <span data-ttu-id="91c05-122">En el archivo de configuración del cliente, WCF no puede diferenciar entre los parámetros de servicio y de cliente.</span><span class="sxs-lookup"><span data-stu-id="91c05-122">From the client configuration file, WCF cannot differentiate between the service and client parameters.</span></span> <span data-ttu-id="91c05-123">Por lo tanto, WCF convierte todos los parámetros en un espacio de nombres de la versión de confianza 1,3.</span><span class="sxs-lookup"><span data-stu-id="91c05-123">Therefore WCF converts all the parameters to a Trust version 1.3 namespace.</span></span>  
  
 <span data-ttu-id="91c05-124">WCF controla los `KeyType` `KeySize` elementos, y `TokenType` como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="91c05-124">WCF handles the `KeyType`, `KeySize`, and `TokenType` elements as follows:</span></span>  
  
- <span data-ttu-id="91c05-125">Descargue el WSDL, cree el enlace y asigne `KeyType`, `KeySize` y `TokenType` de los parámetros RP.</span><span class="sxs-lookup"><span data-stu-id="91c05-125">Download the WSDL, create the binding, and assign `KeyType`, `KeySize`, and `TokenType` from the RP parameters.</span></span> <span data-ttu-id="91c05-126">A continuación se genera el archivo de configuración del cliente.</span><span class="sxs-lookup"><span data-stu-id="91c05-126">The client configuration file is then generated.</span></span>  
  
- <span data-ttu-id="91c05-127">Ahora, el cliente puede cambiar cualquier parámetro del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="91c05-127">The client can now change any parameter in the configuration file.</span></span>  
  
- <span data-ttu-id="91c05-128">Durante el tiempo de ejecución, WCF copia todos los parámetros especificados en la `AdditionalTokenParameters` sección del archivo de configuración del cliente `KeyType` , excepto, `KeySize` y `TokenType` , porque estos parámetros se tienen en cuenta durante la generación del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="91c05-128">During runtime, WCF copies all parameters specified into the `AdditionalTokenParameters` section of the client configuration file except `KeyType`, `KeySize` and `TokenType`, because these parameters are accounted for during the configuration file generation.</span></span>  
  
## <a name="rp-trust-13-and-sts-trust-feb-2005"></a><span data-ttu-id="91c05-129">RP Trust 1.3 y STS Trust Feb 2005</span><span class="sxs-lookup"><span data-stu-id="91c05-129">RP Trust 1.3 and STS Trust Feb 2005</span></span>  

 <span data-ttu-id="91c05-130">El WSDL de RP contiene los elementos siguientes en la sección `RequestSecurityTokenTemplate`:</span><span class="sxs-lookup"><span data-stu-id="91c05-130">The WSDL for RP contains the following elements in the `RequestSecurityTokenTemplate` section:</span></span>  
  
- `CanonicalizationAlgorithm`  
  
- `EncryptionAlgorithm`  
  
- `EncryptWith`  
  
- `SignWith`  
  
- `KeySize`  
  
- `KeyType`  
  
- `KeyWrapAlgorithm`  
  
 <span data-ttu-id="91c05-131">El archivo de configuración del cliente tiene un elemento `secondaryParamters` que contiene los parámetros especificados por RP.</span><span class="sxs-lookup"><span data-stu-id="91c05-131">The client configuration file contains a `secondaryParamters` element that wraps the parameters specified by the RP.</span></span>  
  
 <span data-ttu-id="91c05-132">WCF copia todos los parámetros especificados en la `SecondaryParameters` sección en el elemento RST de nivel superior, pero no los convierte en el espacio de nombres 2005 WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="91c05-132">WCF copies all the parameters specified within the `SecondaryParameters` section to the top-level RST element, but does not convert them to the 2005 WS-Trust namespace.</span></span>
