---
title: Recursos del sistema operativo necesarios para WCF
ms.date: 03/30/2017
ms.assetid: cdd9a331-53fe-4e0d-bdfe-782264aec5c9
ms.openlocfilehash: c2c26d769424a8d0655591cb10b4b13df8a15884
ms.sourcegitcommit: 9b2ef64c4fc10a4a10f28a223d60d17d7d249ee8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/26/2019
ms.locfileid: "72961135"
---
# <a name="operating-system-resources-required-by-wcf"></a><span data-ttu-id="b738f-102">Recursos del sistema operativo necesarios para WCF</span><span class="sxs-lookup"><span data-stu-id="b738f-102">Operating System Resources Required by WCF</span></span>

<span data-ttu-id="b738f-103">Windows Communication Foundation (WCF) depende de varios recursos proporcionados por el sistema operativo para que funcionen.</span><span class="sxs-lookup"><span data-stu-id="b738f-103">Windows Communication Foundation (WCF) depends on several resources that are provided by the operating system to function.</span></span> <span data-ttu-id="b738f-104">En la tabla siguiente se enumeran esos recursos:</span><span class="sxs-lookup"><span data-stu-id="b738f-104">The following table lists those resources:</span></span>

|<span data-ttu-id="b738f-105">Recurso</span><span class="sxs-lookup"><span data-stu-id="b738f-105">Resource</span></span>|<span data-ttu-id="b738f-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="b738f-106">Description</span></span>|
|--------------|-----------------|
|<span data-ttu-id="b738f-107">Microsoft DTC (Coordinador de transacciones distribuidas)</span><span class="sxs-lookup"><span data-stu-id="b738f-107">Microsoft Distributed Transaction Coordinator (MSDTC)</span></span>|<span data-ttu-id="b738f-108">Requerido para admitir las transacciones de OleTx.</span><span class="sxs-lookup"><span data-stu-id="b738f-108">Required to support OleTx transactions.</span></span>|
|<span data-ttu-id="b738f-109">Internet Information Services (IIS)</span><span class="sxs-lookup"><span data-stu-id="b738f-109">Internet Information Services (IIS)</span></span>|<span data-ttu-id="b738f-110">Requerido si quiere usar IIS para hospedar su aplicación.</span><span class="sxs-lookup"><span data-stu-id="b738f-110">Required if you want to use IIS to host your application.</span></span>|
|<span data-ttu-id="b738f-111">Servicio de activación de procesos de Windows (WAS)</span><span class="sxs-lookup"><span data-stu-id="b738f-111">Windows Process Activation Service (WAS)</span></span>|<span data-ttu-id="b738f-112">Requerido si desea utilizar WAS para hospedar su aplicación.</span><span class="sxs-lookup"><span data-stu-id="b738f-112">Required if you want to use WAS to host your application.</span></span>|
