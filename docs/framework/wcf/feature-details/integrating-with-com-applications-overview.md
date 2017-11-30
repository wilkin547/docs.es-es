---
title: "Integración con la información general de las aplicaciones COM"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: COM [WCF], integration overview
ms.assetid: 02c5697f-6e2e-47d6-b715-f3a28aebfbd5
caps.latest.revision: "17"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4e995fc66a925cb0ebe272c9dceca1ba63b9459d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="integrating-with-com-applications-overview"></a><span data-ttu-id="39073-102">Integración con la información general de las aplicaciones COM</span><span class="sxs-lookup"><span data-stu-id="39073-102">Integrating with COM Applications Overview</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="39073-103"> proporciona un entorno enriquecido al desarrollador del código administrado para crear aplicaciones conectadas.</span><span class="sxs-lookup"><span data-stu-id="39073-103"> provides the managed code developer with a rich environment for creating connected applications.</span></span> <span data-ttu-id="39073-104">Sin embargo, si tiene una inversión sustancial en código basado en COM no administrado y no desea migrar, aún podrá integrar directamente los servicios web de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] en el código existente mediante el moniker del servicio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="39073-104">However, if you have a substantial investment in unmanaged COM-based code and do not want to migrate, you can still integrate [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Web services directly into your existing code by using the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service moniker.</span></span> <span data-ttu-id="39073-105">El moniker de servicio se puede utilizar a partir de una gama amplia de entornos de desarrollo basados en COM, como Office VBA, Visual Basic 6.0 o Visual C++ 6.0.</span><span class="sxs-lookup"><span data-stu-id="39073-105">The service moniker can be used from a wide range of COM-based development environments, such as Office VBA, Visual Basic 6.0, or Visual C++ 6.0.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="39073-106">El moniker de servicio utiliza un canal de comunicación [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] para toda la comunicación.</span><span class="sxs-lookup"><span data-stu-id="39073-106">The service moniker uses a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] communication channel for all communication.</span></span> <span data-ttu-id="39073-107">Los mecanismos de identidad y seguridad para ese canal difieren de aquéllos utilizados en los proxies COM y DCOM estándar.</span><span class="sxs-lookup"><span data-stu-id="39073-107">The security and identity mechanisms for that channel differ from those used in standard COM and DCOM proxies.</span></span> <span data-ttu-id="39073-108">Además, dado que el moniker de servicio utiliza un canal de comunicación [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], el período de tiempo de espera predeterminado es un minuto para todas las llamadas.</span><span class="sxs-lookup"><span data-stu-id="39073-108">In addition, because the service moniker uses a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] communication channel the default timeout period is one minute for all calls.</span></span>  
  
 <span data-ttu-id="39073-109">El moniker de servicio se utiliza con la función `GetObject` para proporcionar un enfoque fuertemente tipado, específico de COM al desarrollador no administrado con el fin de llamar a los servicios web de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="39073-109">The service moniker is used with the `GetObject` function to provide the unmanaged developer with a strongly-typed, COM-specific approach for calling [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Web services.</span></span> <span data-ttu-id="39073-110">Esto requiere una definición local, visible a través de COM del contrato de servicio web de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] y el enlace que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="39073-110">This requires a local, COM-visible definition of the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Web service contract and the binding that is to be used.</span></span> <span data-ttu-id="39073-111">Al igual que otros clientes [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], el moniker de servicio debe construir un canal con tipo al servicio, aunque esta construcción del canal se produce de forma transparente en el programador COM en la primera llamada al método.</span><span class="sxs-lookup"><span data-stu-id="39073-111">Like other [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] clients, the service moniker must construct a typed channel to the service, though this channel construction occurs transparently to the COM programmer on the first method call.</span></span>  
  
 <span data-ttu-id="39073-112">Al igual que otros clientes [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], al utilizar el moniker, las aplicaciones especifican la dirección, el enlace y el contrato para comunicarse con un servicio.</span><span class="sxs-lookup"><span data-stu-id="39073-112">In common with other [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] clients, when using the moniker, applications specify the address, binding and contract to communicate with a service.</span></span> <span data-ttu-id="39073-113">El contrato se puede especificar de una de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="39073-113">The contract can be specified in one of the following ways:</span></span>  
  
-   <span data-ttu-id="39073-114">Contrato con tipo: el contrato se registra como un tipo visible COM en el equipo cliente.</span><span class="sxs-lookup"><span data-stu-id="39073-114">Typed contract – the contract is registered as a COM visible type on the client machine.</span></span>  
  
-   <span data-ttu-id="39073-115">Contrato de WSDL: el contrato se proporciona con la forma de un documento WSDL.</span><span class="sxs-lookup"><span data-stu-id="39073-115">WSDL contract – the contract is supplied in the form of a WSDL document.</span></span>  
  
-   <span data-ttu-id="39073-116">Contrato de MEX: el contrato se recupera en el tiempo de ejecución a partir de un extremo de intercambio de metadatos (MEX).</span><span class="sxs-lookup"><span data-stu-id="39073-116">MEX contract – the contract is retrieved at runtime from a Metadata Exchange (MEX) endpoint.</span></span>  
  
## <a name="parameters-supported-by-the-service-moniker"></a><span data-ttu-id="39073-117">Parámetros admitidos por el moniker de servicio</span><span class="sxs-lookup"><span data-stu-id="39073-117">Parameters Supported by the Service Moniker</span></span>  
 <span data-ttu-id="39073-118">En la tabla siguiente se muestran los parámetros admitidos por el moniker de servicio.</span><span class="sxs-lookup"><span data-stu-id="39073-118">The following table shows the parameters that are supported by the service moniker.</span></span>  
  
|<span data-ttu-id="39073-119">Parámetro</span><span class="sxs-lookup"><span data-stu-id="39073-119">Parameter</span></span>|<span data-ttu-id="39073-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="39073-120">Description</span></span>|  
|---------------|-----------------|  
|`address`|<span data-ttu-id="39073-121">Ubicación de URL del servicio.</span><span class="sxs-lookup"><span data-stu-id="39073-121">URL location of the service.</span></span>|  
|`binding`|<span data-ttu-id="39073-122">Nombre de sección de enlace desde la configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="39073-122">Binding section name from the application configuration.</span></span>|  
|`bindingConfiguration`|<span data-ttu-id="39073-123">Instancia del enlace con nombre desde la sección de enlace con nombre.</span><span class="sxs-lookup"><span data-stu-id="39073-123">Named binding instance from within the named binding section.</span></span>|  
|`contract`|<span data-ttu-id="39073-124">Identificador de interfaz (IID) que representa el contrato de servicio o el nombre del contrato (de MEX).</span><span class="sxs-lookup"><span data-stu-id="39073-124">Interface identifier (IID) that represents the service contract or the contract name (from MEX).</span></span>|  
|`wsdl`|<span data-ttu-id="39073-125">Documento WSDL que proporciona un formulario alternativo de definición de contrato.</span><span class="sxs-lookup"><span data-stu-id="39073-125">WSDL document that provides an alternative form of contract definition.</span></span>|  
|`spnIdentity`|<span data-ttu-id="39073-126">Identidad del nombre de entidad de seguridad de servidor (SPN) que se va a utilizar para comunicarse con el servicio.</span><span class="sxs-lookup"><span data-stu-id="39073-126">Server principal name (SPN) identity to be used to communicate with the service.</span></span>|  
|`upnIdentity`|<span data-ttu-id="39073-127">Identidad del nombre principal del usuario (UPN) que se va a utilizar para comunicarse con el servicio.</span><span class="sxs-lookup"><span data-stu-id="39073-127">User principal name (UPN) identity to be used to communicate with the service.</span></span>|  
|`dnsIdentity`|<span data-ttu-id="39073-128">Identidad de DNS que se va a utilizar para comunicarse con el servicio.</span><span class="sxs-lookup"><span data-stu-id="39073-128">DNS identity to be used to communicate with the service.</span></span>|  
|`mexAddress`|<span data-ttu-id="39073-129">Ubicación de la dirección URL del punto de conexión de intercambio de metadatos (MEX) del servicio.</span><span class="sxs-lookup"><span data-stu-id="39073-129">URL location of the Metadata Exchange (MEX) endpoint of the service.</span></span>|  
|`mexBinding`|<span data-ttu-id="39073-130">El nombre de la sección de enlace a partir de la configuración de la aplicación para conectarse con el punto de conexión MEX.</span><span class="sxs-lookup"><span data-stu-id="39073-130">Binding section name from the application configuration to connect with the MEX endpoint.</span></span>|  
|`mexBindingConfiguration`|<span data-ttu-id="39073-131">Instancia de enlace con nombre desde la que la sección de enlace con nombre se conecta con el punto de conexión MEX.</span><span class="sxs-lookup"><span data-stu-id="39073-131">Named binding instance from within the named binding section to connect with the MEX endpoint.</span></span>|  
|`bindingNamespace`|<span data-ttu-id="39073-132">El espacio de nombres del nombre de la sección de enlace desde el MEX recuperado.</span><span class="sxs-lookup"><span data-stu-id="39073-132">Namespace of the binding section name from the retrieved MEX.</span></span>|  
|`contractNamespace`|<span data-ttu-id="39073-133">El espacio de nombres del contrato desde el MEX recuperado.</span><span class="sxs-lookup"><span data-stu-id="39073-133">Namespace of the contract from the retrieved MEX.</span></span>|  
|`mexSpnIdentity`|<span data-ttu-id="39073-134">Identidad del nombre de entidad de seguridad de servidor (SPN) que se va a utilizar para comunicarse con el punto de conexión MEX.</span><span class="sxs-lookup"><span data-stu-id="39073-134">Server principal name (SPN) identity to be used to communicate with the MEX endpoint.</span></span>|  
|`mexUpnIdentity`|<span data-ttu-id="39073-135">Identidad del nombre principal del usuario (UPN) que se va a utilizar para comunicarse con el punto de conexión MEX.</span><span class="sxs-lookup"><span data-stu-id="39073-135">User principal name (UPN) identity to be used to communicate with the MEX endpoint.</span></span>|  
|`mexDnsIdentity`|<span data-ttu-id="39073-136">Identidad de DNS que se va a utilizar para comunicarse con el punto de conexión MEX.</span><span class="sxs-lookup"><span data-stu-id="39073-136">DNS identity to be used to communicate with the MEX endpoint.</span></span>|  
|`serializer`|<span data-ttu-id="39073-137">Especifique el uso de "xml" o serializador de "datacontract."</span><span class="sxs-lookup"><span data-stu-id="39073-137">Specify the use of either the "xml" or "datacontract" serializer.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="39073-138">Incluso cuando se utiliza con clientes completamente basados en COM, el moniker de servicio exige que se instale [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] y .NET Framework 2.0 compatible en el equipo cliente.</span><span class="sxs-lookup"><span data-stu-id="39073-138">Even when used with entirely COM-based clients, the service moniker requires [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] and the supporting .NET Framework 2.0 to be installed on the client computer.</span></span> <span data-ttu-id="39073-139">También es fundamental que las aplicaciones cliente que utilizan el moniker de servicio carguen la versión adecuada del tiempo de ejecución de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="39073-139">It is also critical that client applications that use the service moniker load the appropriate version of the .NET Framework runtime.</span></span> <span data-ttu-id="39073-140">Al utilizar el moniker en aplicaciones de Office, es posible que sea necesario un archivo de configuración para asegurarse de que se carga la versión de marco correcta.</span><span class="sxs-lookup"><span data-stu-id="39073-140">When using the moniker within Office applications, a configuration file may be required to ensure that the correct framework version is loaded.</span></span> <span data-ttu-id="39073-141">Por ejemplo, con Excel, el texto siguiente debería colocarse en un archivo denominado Excel.exe.config en el mismo directorio que el archivo Excel.exe:</span><span class="sxs-lookup"><span data-stu-id="39073-141">For example, with Excel, the following text should be placed in a file called Excel.exe.config in the same directory as the Excel.exe file:</span></span>  
>   
>  `<?xml version="1.0" encoding="utf-8"?>`  
>   
>  <span data-ttu-id="39073-142">`<configuration xmlns=` `http://schemas.microsoft.com/.NetConfiguration/v2.0` `>`</span><span class="sxs-lookup"><span data-stu-id="39073-142">`<configuration xmlns=` `http://schemas.microsoft.com/.NetConfiguration/v2.0` `>`</span></span>  
>   
>  `<startup>`  
>   
>  `<requiredRuntime version="v2.0.50727" />`  
>   
>  `</startup>`  
>   
>  `</configuration>`  
  
## <a name="see-also"></a><span data-ttu-id="39073-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="39073-143">See Also</span></span>  
 [<span data-ttu-id="39073-144">Cómo: registrar y configurar un Moniker de servicio</span><span class="sxs-lookup"><span data-stu-id="39073-144">How to: Register and Configure a Service Moniker</span></span>](../../../../docs/framework/wcf/feature-details/how-to-register-and-configure-a-service-moniker.md)
