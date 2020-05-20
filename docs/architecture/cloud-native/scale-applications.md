---
title: Escalado de aplicaciones nativas en la nube
description: Escalado de aplicaciones nativas en la nube con Azure Kubernetes Service y Azure Functions para satisfacer la demanda de los usuarios de una manera rentable.
ms.date: 05/13/2020
ms.openlocfilehash: d425976eed248461a9c2e4fe03596f9f6dfd2eba
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83613738"
---
# <a name="scaling-cloud-native-applications"></a><span data-ttu-id="0a0b9-103">Escalado de aplicaciones nativas en la nube</span><span class="sxs-lookup"><span data-stu-id="0a0b9-103">Scaling cloud-native applications</span></span>

<span data-ttu-id="0a0b9-104">Una de las ventajas más frecuentes de pasar a un entorno de hospedaje en la nube es la escalabilidad.</span><span class="sxs-lookup"><span data-stu-id="0a0b9-104">One of the most-often touted advantages of moving to a cloud hosting environment is scalability.</span></span> <span data-ttu-id="0a0b9-105">Escalabilidad, o la capacidad de una aplicación para aceptar la carga de usuarios adicional sin poner en peligro el rendimiento de cada usuario.</span><span class="sxs-lookup"><span data-stu-id="0a0b9-105">Scalability, or the ability for an application to accept additional user load without compromising performance for each user.</span></span> <span data-ttu-id="0a0b9-106">La mayoría de las veces se consigue dividiendo una aplicación en pequeñas partes a las que se les puede dar cada uno de los recursos que requieran.</span><span class="sxs-lookup"><span data-stu-id="0a0b9-106">It's most often achieved by breaking up an application into small pieces that can each be given whatever resources they require.</span></span> <span data-ttu-id="0a0b9-107">Los proveedores de nube permiten una escalabilidad masiva en cualquier momento y lugar del mundo.</span><span class="sxs-lookup"><span data-stu-id="0a0b9-107">Cloud vendors enable massive scalability anytime and anywhere in the world.</span></span>

 <span data-ttu-id="0a0b9-108">En este capítulo, se describen las tecnologías que permiten escalar aplicaciones nativas en la nube para satisfacer la demanda de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="0a0b9-108">In this chapter, we discuss technologies that enable cloud-native applications to scale to meet user demand.</span></span> <span data-ttu-id="0a0b9-109">Estas tecnologías incluyen:</span><span class="sxs-lookup"><span data-stu-id="0a0b9-109">These technologies include:</span></span>

- <span data-ttu-id="0a0b9-110">Contenedores</span><span class="sxs-lookup"><span data-stu-id="0a0b9-110">Containers</span></span>
- <span data-ttu-id="0a0b9-111">Orquestadores</span><span class="sxs-lookup"><span data-stu-id="0a0b9-111">Orchestrators</span></span>
- <span data-ttu-id="0a0b9-112">Informática sin servidor</span><span class="sxs-lookup"><span data-stu-id="0a0b9-112">Serverless computing</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="0a0b9-113">[Anterior](centralized-configuration.md)
>[Siguiente](leverage-containers-orchestrators.md)</span><span class="sxs-lookup"><span data-stu-id="0a0b9-113">[Previous](centralized-configuration.md)
[Next](leverage-containers-orchestrators.md)</span></span>
