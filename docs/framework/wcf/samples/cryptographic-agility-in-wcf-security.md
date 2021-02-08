---
description: 'Más información sobre: agilidad criptográfica en la seguridad de WCF'
title: Agilidad criptográfica en la seguridad de WCF
ms.date: 03/30/2017
ms.assetid: c2c549e5-ac19-40c5-b686-8f67f52b6dbf
ms.openlocfilehash: ab46034b16a846f7399220480fc928655d931be0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99778352"
---
# <a name="cryptographic-agility-in-wcf-security"></a><span data-ttu-id="961ab-103">Agilidad criptográfica en la seguridad de WCF</span><span class="sxs-lookup"><span data-stu-id="961ab-103">Cryptographic agility in WCF security</span></span>

<span data-ttu-id="961ab-104">En este ejemplo se muestra cómo especificar en un algoritmo estándar o personalizado para proporcionar una implementación criptográfica de Agile en un servicio y cliente de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="961ab-104">This sample shows how to specify in a standard/custom algorithm to provide a cryptographic agile implementation in a Windows Communication Foundation (WCF) client and service.</span></span> <span data-ttu-id="961ab-105">El ejemplo consta de los proyectos siguientes:</span><span class="sxs-lookup"><span data-stu-id="961ab-105">The sample is composed of the following projects:</span></span>

<span data-ttu-id="961ab-106">**Servicio**</span><span class="sxs-lookup"><span data-stu-id="961ab-106">**Service**</span></span>

<span data-ttu-id="961ab-107">Se trata de un servicio WCF autohospedado que implementa la `ICalculator` interfaz y protege el punto de conexión mediante <xref:System.ServiceModel.WSHttpBinding> con la sesión segura y la sesión confiable deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="961ab-107">This is a self-hosted WCF service that implements the `ICalculator` interface and secures the endpoint using the <xref:System.ServiceModel.WSHttpBinding> with secure session and reliable session disabled.</span></span> <span data-ttu-id="961ab-108">El servicio define una clase `SecurityAlgorithmSuite` personalizada para especificar los algoritmos criptográficos que se van a utilizar para la seguridad de los mensajes.</span><span class="sxs-lookup"><span data-stu-id="961ab-108">The service defines a custom `SecurityAlgorithmSuite` class to specify the cryptographic algorithms to be used for message security.</span></span>

<span data-ttu-id="961ab-109">**Cliente**</span><span class="sxs-lookup"><span data-stu-id="961ab-109">**Client**</span></span>

<span data-ttu-id="961ab-110">Se trata de un cliente WCF que tiene acceso al servicio después de la autenticación correcta.</span><span class="sxs-lookup"><span data-stu-id="961ab-110">This is a WCF client that accesses the service after successful authentication.</span></span> <span data-ttu-id="961ab-111">Invoca las operaciones expuestas por la interfaz `ICalculator` e implementadas por el servicio.</span><span class="sxs-lookup"><span data-stu-id="961ab-111">It invokes the operations exposed by the `ICalculator` interface and implemented by the service.</span></span> <span data-ttu-id="961ab-112">El cliente también define la misma clase `SecurityAlgorithmSuite` personalizada para especificar los algoritmos criptográficos que se van a utilizar para el modo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="961ab-112">The client also defines the same custom `SecurityAlgorithmSuite` class to specify the cryptographic algorithms to be used for message security.</span></span>

## <a name="to-use-this-sample"></a><span data-ttu-id="961ab-113">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="961ab-113">To use this sample</span></span>

1. <span data-ttu-id="961ab-114">Abra la solución CryptoAgility. sln en Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="961ab-114">Open the CryptoAgility.sln solution in Visual Studio 2012.</span></span>

2. <span data-ttu-id="961ab-115">Presione CTRL+MAYÚS+B para compilar la solución.</span><span class="sxs-lookup"><span data-stu-id="961ab-115">Press CTRL+SHIFT+B to build the solution.</span></span>

3. <span data-ttu-id="961ab-116">Abra el explorador de archivos y vaya al directorio \WCF\Basic\Security\CryptoAgility\Service\bin y ejecute el archivo service.exe con privilegios de administrador haciendo clic con el botón secundario en service.exe y seleccionando **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="961ab-116">Open File Explorer and navigate to the \WCF\Basic\Security\CryptoAgility\Service\bin directory and run the service.exe file with administrator privileges by right-clicking service.exe and selecting **Run as administrator**.</span></span>

4. <span data-ttu-id="961ab-117">Navegue hasta el directorio \WCF\Basic\Security\CryptoAgility\Client\bin y ejecute el archivo client.exe normalmente.</span><span class="sxs-lookup"><span data-stu-id="961ab-117">Navigate to \WCF\Basic\Security\CryptoAgility\Client\bin directory and run the client.exe file normally.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="961ab-118">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="961ab-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="961ab-119">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="961ab-119">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="961ab-120">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="961ab-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="961ab-121">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="961ab-121">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Security\CryptoAgility`

## <a name="see-also"></a><span data-ttu-id="961ab-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="961ab-122">See also</span></span>

- [<span data-ttu-id="961ab-123">Seguridad en Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="961ab-123">Windows Communication Foundation Security</span></span>](../feature-details/security.md)
