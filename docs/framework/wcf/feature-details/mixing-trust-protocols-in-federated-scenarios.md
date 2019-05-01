---
title: Combinación de protocolos de confianza en escenarios federados
ms.date: 03/30/2017
ms.assetid: d7b5fee9-2246-4b09-b8d7-9e63cb817279
ms.openlocfilehash: ce5c3a1875d84d98068dcc78d8346a88bc0b28f3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62046697"
---
# <a name="mixing-trust-protocols-in-federated-scenarios"></a><span data-ttu-id="6ab52-102">Combinación de protocolos de confianza en escenarios federados</span><span class="sxs-lookup"><span data-stu-id="6ab52-102">Mixing Trust Protocols in Federated Scenarios</span></span>
<span data-ttu-id="6ab52-103">Puede haber situaciones en las que los clientes federados se comuniquen con un servicio y un servicio de tokens de seguridad (STS) que no tengan la misma versión de confianza.</span><span class="sxs-lookup"><span data-stu-id="6ab52-103">There may be scenarios in which federated clients communicate with a service and a Security Token Service (STS) that do not have the same trust version.</span></span> <span data-ttu-id="6ab52-104">El WSDL del servicio puede contener una aserción `RequestSecurityTokenTemplate` con elementos WS-Trust que sean de versiones diferentes que las de STS.</span><span class="sxs-lookup"><span data-stu-id="6ab52-104">The service WSDL can contain a `RequestSecurityTokenTemplate` assertion with WS-Trust elements that are of different versions than the STS.</span></span> <span data-ttu-id="6ab52-105">En tales casos, un cliente de Windows Communication Foundation (WCF) convierte los elementos de WS-Trust recibidos de la `RequestSecurityTokenTemplate` para que coincida con el STS de confianza versión.</span><span class="sxs-lookup"><span data-stu-id="6ab52-105">In such cases, a Windows Communication Foundation (WCF) client converts the WS-Trust elements received from the `RequestSecurityTokenTemplate` to match the STS trust version.</span></span> <span data-ttu-id="6ab52-106">WCF controla las versiones de confianza no coincidentes solo para los enlaces estándares.</span><span class="sxs-lookup"><span data-stu-id="6ab52-106">WCF handles mismatched trust versions only for standard bindings.</span></span> <span data-ttu-id="6ab52-107">Todos los parámetros del algoritmo estándar que son reconocidos por WCF forman parte del enlace estándar.</span><span class="sxs-lookup"><span data-stu-id="6ab52-107">All standard algorithm parameters that are recognized by WCF are part of the standard binding.</span></span> <span data-ttu-id="6ab52-108">En este tema se describe el comportamiento WCF con distintas configuraciones de confianza entre el servicio y el STS.</span><span class="sxs-lookup"><span data-stu-id="6ab52-108">This topic describes the WCF behavior with various trust settings between the service and the STS.</span></span>  
  
## <a name="rp-feb-2005-and-sts-feb-2005"></a><span data-ttu-id="6ab52-109">RP Feb 2005 y STS Feb 2005</span><span class="sxs-lookup"><span data-stu-id="6ab52-109">RP Feb 2005 and STS Feb 2005</span></span>  
 <span data-ttu-id="6ab52-110">El WSDL de Usuario de confianza (RP) contiene los elementos siguientes en la sección `RequestSecurityTokenTemplate`:</span><span class="sxs-lookup"><span data-stu-id="6ab52-110">The WSDL for Relying Party (RP) contains the following elements within the `RequestSecurityTokenTemplate` section:</span></span>  
  
- `CanonicalizationAlgorithm`  
  
- `EncryptionAlgorithm`  
  
- `EncryptWith`  
  
- `SignWith`  
  
- `KeySize`  
  
- `KeyType`  
  
 <span data-ttu-id="6ab52-111">El archivo de configuración del cliente contiene una lista de parámetros.</span><span class="sxs-lookup"><span data-stu-id="6ab52-111">The client configuration file contains a list of parameters.</span></span>  
  
 <span data-ttu-id="6ab52-112">WCF no puede diferenciar entre los parámetros del cliente y el servicio; Agrega todos los parámetros y los envía en el `RequestSecurityTokenTemplate` (RST).</span><span class="sxs-lookup"><span data-stu-id="6ab52-112">WCF cannot differentiate between the client and service parameters; it adds all the parameters and sends them in the `RequestSecurityTokenTemplate` (RST).</span></span>  
  
## <a name="rp-trust-13-and-sts-trust-13"></a><span data-ttu-id="6ab52-113">RP Trust 1.3 y STS Trust 1.3</span><span class="sxs-lookup"><span data-stu-id="6ab52-113">RP Trust 1.3 and STS Trust 1.3</span></span>  
 <span data-ttu-id="6ab52-114">El WSDL de RP contiene los elementos siguientes en la sección `RequestSecurityTokenTemplate`:</span><span class="sxs-lookup"><span data-stu-id="6ab52-114">The WSDL for RP contains the following elements within the `RequestSecurityTokenTemplate` section:</span></span>  
  
- `CanonicalizationAlgorithm`  
  
- `EncryptionAlgorithm`  
  
- `EncryptWith`  
  
- `SignWith`  
  
- `KeySize`  
  
- `KeyType`  
  
- `KeyWrapAlgorithm`  
  
 <span data-ttu-id="6ab52-115">El archivo de configuración del cliente tiene un elemento `secondaryParameters` que contiene los parámetros especificados por RP.</span><span class="sxs-lookup"><span data-stu-id="6ab52-115">The client configuration file contains a `secondaryParameters` element that wraps the parameters specified by the RP.</span></span>  
  
 <span data-ttu-id="6ab52-116">WCF quita el `EncryptionAlgorithm`, `CanonicalizationAlgorithm` y `KeyWrapAlgorithm` elementos desde el elemento de nivel superior bajo RST si éstos están presentes dentro del `SecondaryParameters` elemento.</span><span class="sxs-lookup"><span data-stu-id="6ab52-116">WCF removes the `EncryptionAlgorithm`, `CanonicalizationAlgorithm` and `KeyWrapAlgorithm` elements from the top-level element under the RST if these are present inside the `SecondaryParameters` element.</span></span> <span data-ttu-id="6ab52-117">WCF se anexa el `SecondaryParameters` elemento al RST de salida sin modificar.</span><span class="sxs-lookup"><span data-stu-id="6ab52-117">WCF appends the `SecondaryParameters` element to the outgoing RST unmodified.</span></span>  
  
## <a name="rp-trust-feb-2005-and-sts-trust-13"></a><span data-ttu-id="6ab52-118">RP Trust Feb 2005 y STS Trust 1.3</span><span class="sxs-lookup"><span data-stu-id="6ab52-118">RP Trust Feb 2005 and STS Trust 1.3</span></span>  
 <span data-ttu-id="6ab52-119">El WSDL de RP contiene los elementos siguientes en la sección `RequestSecurityTokenTemplate`:</span><span class="sxs-lookup"><span data-stu-id="6ab52-119">The WSDL for RP contains the following elements in the `RequestSecurityTokenTemplate` section:</span></span>  
  
- `CanonicalizationAlgorithm`  
  
- `EncryptionAlgorithm`  
  
- `EncryptWith`  
  
- `SignWith`  
  
- `KeySize`  
  
- `KeyType`  
  
 <span data-ttu-id="6ab52-120">El archivo de configuración del cliente contiene una lista de parámetros.</span><span class="sxs-lookup"><span data-stu-id="6ab52-120">The client configuration file contains a list of parameters.</span></span>  
  
 <span data-ttu-id="6ab52-121">Desde el archivo de configuración de cliente WCF no puede diferenciar entre los parámetros de servicio y cliente.</span><span class="sxs-lookup"><span data-stu-id="6ab52-121">From the client configuration file, WCF cannot differentiate between the service and client parameters.</span></span> <span data-ttu-id="6ab52-122">Por lo tanto, WCF convierte todos los parámetros en un espacio de nombres de la versión 1.3 de confianza.</span><span class="sxs-lookup"><span data-stu-id="6ab52-122">Therefore WCF converts all the parameters to a Trust version 1.3 namespace.</span></span>  
  
 <span data-ttu-id="6ab52-123">WCF controla la `KeyType`, `KeySize`, y `TokenType` elementos como sigue:</span><span class="sxs-lookup"><span data-stu-id="6ab52-123">WCF handles the `KeyType`, `KeySize`, and `TokenType` elements as follows:</span></span>  
  
- <span data-ttu-id="6ab52-124">Descargue el WSDL, cree el enlace y asigne `KeyType`, `KeySize` y `TokenType` de los parámetros RP.</span><span class="sxs-lookup"><span data-stu-id="6ab52-124">Download the WSDL, create the binding, and assign `KeyType`, `KeySize`, and `TokenType` from the RP parameters.</span></span> <span data-ttu-id="6ab52-125">A continuación se genera el archivo de configuración del cliente.</span><span class="sxs-lookup"><span data-stu-id="6ab52-125">The client configuration file is then generated.</span></span>  
  
- <span data-ttu-id="6ab52-126">Ahora, el cliente puede cambiar cualquier parámetro del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="6ab52-126">The client can now change any parameter in the configuration file.</span></span>  
  
- <span data-ttu-id="6ab52-127">En tiempo de ejecución, WCF copia todos los parámetros especificados en el `AdditionalTokenParameters` sección del archivo de configuración del cliente excepto `KeyType`, `KeySize` y `TokenType`, ya que estos parámetros se tienen en cuenta durante el archivo de configuración generación.</span><span class="sxs-lookup"><span data-stu-id="6ab52-127">During runtime, WCF copies all parameters specified into the `AdditionalTokenParameters` section of the client configuration file except `KeyType`, `KeySize` and `TokenType`, because these parameters are accounted for during the configuration file generation.</span></span>  
  
## <a name="rp-trust-13-and-sts-trust-feb-2005"></a><span data-ttu-id="6ab52-128">RP Trust 1.3 y STS Trust Feb 2005</span><span class="sxs-lookup"><span data-stu-id="6ab52-128">RP Trust 1.3 and STS Trust Feb 2005</span></span>  
 <span data-ttu-id="6ab52-129">El WSDL de RP contiene los elementos siguientes en la sección `RequestSecurityTokenTemplate`:</span><span class="sxs-lookup"><span data-stu-id="6ab52-129">The WSDL for RP contains the following elements in the `RequestSecurityTokenTemplate` section:</span></span>  
  
- `CanonicalizationAlgorithm`  
  
- `EncryptionAlgorithm`  
  
- `EncryptWith`  
  
- `SignWith`  
  
- `KeySize`  
  
- `KeyType`  
  
- `KeyWrapAlgorithm`  
  
 <span data-ttu-id="6ab52-130">El archivo de configuración del cliente tiene un elemento `secondaryParamters` que contiene los parámetros especificados por RP.</span><span class="sxs-lookup"><span data-stu-id="6ab52-130">The client configuration file contains a `secondaryParamters` element that wraps the parameters specified by the RP.</span></span>  
  
 <span data-ttu-id="6ab52-131">WCF copia todos los parámetros especificados dentro de la `SecondaryParameters` sección para el elemento RST de nivel superior, pero no se convierten en el espacio de nombres de WS-Trust de 2005.</span><span class="sxs-lookup"><span data-stu-id="6ab52-131">WCF copies all the parameters specified within the `SecondaryParameters` section to the top-level RST element, but does not convert them to the 2005 WS-Trust namespace.</span></span>
