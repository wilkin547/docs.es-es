---
title: Agilidad criptográfica en la seguridad de WCF
ms.date: 03/30/2017
ms.assetid: c2c549e5-ac19-40c5-b686-8f67f52b6dbf
ms.openlocfilehash: b8e3b6dc62baf31901520d7f5edac0529e937016
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490938"
---
# <a name="cryptographic-agility-in-wcf-security"></a><span data-ttu-id="dc837-102">Agilidad criptográfica en la seguridad de WCF</span><span class="sxs-lookup"><span data-stu-id="dc837-102">Cryptographic agility in WCF security</span></span>

<span data-ttu-id="dc837-103">En este ejemplo se muestra cómo especificar un algoritmo estándar o personalizado para proporcionar una implementación criptográfica agile en un cliente de Windows Communication Foundation (WCF) y el servicio.</span><span class="sxs-lookup"><span data-stu-id="dc837-103">This sample shows how to specify in a standard/custom algorithm to provide a cryptographic agile implementation in a Windows Communication Foundation (WCF) client and service.</span></span> <span data-ttu-id="dc837-104">El ejemplo consta de los proyectos siguientes:</span><span class="sxs-lookup"><span data-stu-id="dc837-104">The sample is composed of the following projects:</span></span>

<span data-ttu-id="dc837-105">**Servicio**</span><span class="sxs-lookup"><span data-stu-id="dc837-105">**Service**</span></span>

<span data-ttu-id="dc837-106">Se trata de un servicio WCF autohospedado que implementa el `ICalculator` interfaz y protege el punto de conexión mediante el <xref:System.ServiceModel.WSHttpBinding> con sesión segura y sesión confiable deshabilitadas.</span><span class="sxs-lookup"><span data-stu-id="dc837-106">This is a self-hosted WCF service that implements the `ICalculator` interface and secures the endpoint using the <xref:System.ServiceModel.WSHttpBinding> with secure session and reliable session disabled.</span></span> <span data-ttu-id="dc837-107">El servicio define una clase `SecurityAlgorithmSuite` personalizada para especificar los algoritmos criptográficos que se van a utilizar para la seguridad de los mensajes.</span><span class="sxs-lookup"><span data-stu-id="dc837-107">The service defines a custom `SecurityAlgorithmSuite` class to specify the cryptographic algorithms to be used for message security.</span></span>

<span data-ttu-id="dc837-108">**Cliente**</span><span class="sxs-lookup"><span data-stu-id="dc837-108">**Client**</span></span>

<span data-ttu-id="dc837-109">Se trata de un cliente WCF que tiene acceso al servicio tras una autenticación correcta.</span><span class="sxs-lookup"><span data-stu-id="dc837-109">This is a WCF client that accesses the service after successful authentication.</span></span> <span data-ttu-id="dc837-110">Invoca las operaciones expuestas por la interfaz `ICalculator` e implementadas por el servicio.</span><span class="sxs-lookup"><span data-stu-id="dc837-110">It invokes the operations exposed by the `ICalculator` interface and implemented by the service.</span></span> <span data-ttu-id="dc837-111">El cliente también define la misma clase `SecurityAlgorithmSuite` personalizada para especificar los algoritmos criptográficos que se van a utilizar para el modo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="dc837-111">The client also defines the same custom `SecurityAlgorithmSuite` class to specify the cryptographic algorithms to be used for message security.</span></span>

## <a name="to-use-this-sample"></a><span data-ttu-id="dc837-112">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="dc837-112">To use this sample</span></span>

1. <span data-ttu-id="dc837-113">Abra la solución CryptoAgility.sln en Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="dc837-113">Open the CryptoAgility.sln solution in Visual Studio 2012.</span></span>

2. <span data-ttu-id="dc837-114">Presione Ctrl+MAYÚS+B para compilar la solución.</span><span class="sxs-lookup"><span data-stu-id="dc837-114">Press CTRL+SHIFT+B to build the solution.</span></span>

3. <span data-ttu-id="dc837-115">Abra el Explorador de archivos y navegue al directorio \WCF\Basic\Security\CryptoAgility\Service\bin y ejecute el archivo service.exe con privilegios de administrador haciendo clic en service.exe y seleccionando **ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="dc837-115">Open File Explorer and navigate to the \WCF\Basic\Security\CryptoAgility\Service\bin directory and run the service.exe file with administrator privileges by right-clicking service.exe and selecting **Run as administrator**.</span></span>

4. <span data-ttu-id="dc837-116">Navegue hasta el directorio \WCF\Basic\Security\CryptoAgility\Client\bin y ejecute el archivo client.exe normalmente.</span><span class="sxs-lookup"><span data-stu-id="dc837-116">Navigate to \WCF\Basic\Security\CryptoAgility\Client\bin directory and run the client.exe file normally.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dc837-117">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="dc837-117">The samples may already be installed on your machine.</span></span> <span data-ttu-id="dc837-118">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="dc837-118">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="dc837-119">Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="dc837-119">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="dc837-120">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="dc837-120">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Security\CryptoAgility`

## <a name="see-also"></a><span data-ttu-id="dc837-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="dc837-121">See also</span></span>

- [<span data-ttu-id="dc837-122">Seguridad de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="dc837-122">Windows Communication Foundation Security</span></span>](../feature-details/security.md)
