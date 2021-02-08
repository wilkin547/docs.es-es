---
description: 'Más información sobre: recursos del sistema operativo necesarios para WCF'
title: Recursos del sistema operativo necesarios para WCF
ms.date: 03/30/2017
ms.assetid: cdd9a331-53fe-4e0d-bdfe-782264aec5c9
ms.openlocfilehash: 717ab2074c0dcf840919c2bd8afa2641e106ac11
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99779223"
---
# <a name="operating-system-resources-required-by-wcf"></a><span data-ttu-id="ab96b-103">Recursos del sistema operativo necesarios para WCF</span><span class="sxs-lookup"><span data-stu-id="ab96b-103">Operating System Resources Required by WCF</span></span>

<span data-ttu-id="ab96b-104">Windows Communication Foundation (WCF) depende de varios recursos proporcionados por el sistema operativo para que funcionen.</span><span class="sxs-lookup"><span data-stu-id="ab96b-104">Windows Communication Foundation (WCF) depends on several resources that are provided by the operating system to function.</span></span> <span data-ttu-id="ab96b-105">En la tabla siguiente se enumeran esos recursos:</span><span class="sxs-lookup"><span data-stu-id="ab96b-105">The following table lists those resources:</span></span>

|<span data-ttu-id="ab96b-106">Resource</span><span class="sxs-lookup"><span data-stu-id="ab96b-106">Resource</span></span>|<span data-ttu-id="ab96b-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="ab96b-107">Description</span></span>|
|--------------|-----------------|
|<span data-ttu-id="ab96b-108">Microsoft DTC (Coordinador de transacciones distribuidas) </span><span class="sxs-lookup"><span data-stu-id="ab96b-108">Microsoft Distributed Transaction Coordinator (MSDTC)</span></span>|<span data-ttu-id="ab96b-109">Requerido para admitir las transacciones de OleTx.</span><span class="sxs-lookup"><span data-stu-id="ab96b-109">Required to support OleTx transactions.</span></span>|
|<span data-ttu-id="ab96b-110">Servicios de Internet Information Server (IIS)</span><span class="sxs-lookup"><span data-stu-id="ab96b-110">Internet Information Services (IIS)</span></span>|<span data-ttu-id="ab96b-111">Requerido si quiere usar IIS para hospedar su aplicación.</span><span class="sxs-lookup"><span data-stu-id="ab96b-111">Required if you want to use IIS to host your application.</span></span>|
|<span data-ttu-id="ab96b-112">Servicio de activación de procesos de Windows (WAS)</span><span class="sxs-lookup"><span data-stu-id="ab96b-112">Windows Process Activation Service (WAS)</span></span>|<span data-ttu-id="ab96b-113">Requerido si desea utilizar WAS para hospedar su aplicación.</span><span class="sxs-lookup"><span data-stu-id="ab96b-113">Required if you want to use WAS to host your application.</span></span>|
