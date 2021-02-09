---
description: 'Más información acerca de: Acceso a los servicios Web de aplicaciones (Visual Basic)'
title: Acceso a los servicios web de las aplicaciones
ms.date: 07/20/2015
helpviewer_keywords:
- Web services [Visual Basic], My.WebServices object
- My.WebServices object
- applications [Visual Basic], Web services
ms.assetid: 8ad5405b-e771-42b1-82d3-ce97af2cea9e
ms.openlocfilehash: 4efd35ed7c8f4251a749b85a45242af299a51e6c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797892"
---
# <a name="accessing-application-web-services-visual-basic"></a><span data-ttu-id="57489-103">Acceso a los servicios Web de aplicaciones (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="57489-103">Accessing Application Web Services (Visual Basic)</span></span>

<span data-ttu-id="57489-104">El objeto `My.WebServices` proporciona una instancia de cada servicio Web al que hace referencia el proyecto actual.</span><span class="sxs-lookup"><span data-stu-id="57489-104">The `My.WebServices` object provides an instance of each Web service referenced by the current project.</span></span> <span data-ttu-id="57489-105">Cada una de las instancias se crea a petición.</span><span class="sxs-lookup"><span data-stu-id="57489-105">Each instance is instantiated on demand.</span></span> <span data-ttu-id="57489-106">Puede tener acceso a estos servicios Web a través de las propiedades del objeto `My.WebServices`.</span><span class="sxs-lookup"><span data-stu-id="57489-106">You can access these Web services through the properties of the `My.WebServices` object.</span></span> <span data-ttu-id="57489-107">El nombre de la propiedad es igual que el nombre del servicio Web al que tiene acceso la propiedad.</span><span class="sxs-lookup"><span data-stu-id="57489-107">The name of the property is the same as the name of the Web service that the property accesses.</span></span> <span data-ttu-id="57489-108">Cualquier clase que hereda de <xref:System.Web.Services.Protocols.SoapHttpClientProtocol> es un servicio web.</span><span class="sxs-lookup"><span data-stu-id="57489-108">Any class that inherits from <xref:System.Web.Services.Protocols.SoapHttpClientProtocol> is a Web service.</span></span>

## <a name="tasks"></a><span data-ttu-id="57489-109">Tareas</span><span class="sxs-lookup"><span data-stu-id="57489-109">Tasks</span></span>

<span data-ttu-id="57489-110">La tabla siguiente muestra las posibles maneras de tener acceso a los servicios Web a los que hace referencia una aplicación.</span><span class="sxs-lookup"><span data-stu-id="57489-110">The following table lists possible ways to access Web services referenced by an application.</span></span>

|<span data-ttu-id="57489-111">En</span><span class="sxs-lookup"><span data-stu-id="57489-111">To</span></span>|<span data-ttu-id="57489-112">Vea</span><span class="sxs-lookup"><span data-stu-id="57489-112">See</span></span>|
|---|---|
|<span data-ttu-id="57489-113">Llamar a un servicio Web</span><span class="sxs-lookup"><span data-stu-id="57489-113">Call a Web service</span></span>|[<span data-ttu-id="57489-114">My.WebServices (objeto)</span><span class="sxs-lookup"><span data-stu-id="57489-114">My.WebServices Object</span></span>](../../language-reference/objects/my-webservices-object.md)|
|<span data-ttu-id="57489-115">Llamar de manera asincrónica a un servicio Web y controlar un evento cuando finaliza</span><span class="sxs-lookup"><span data-stu-id="57489-115">Call a Web service asynchronously and handle an event when it completes</span></span>|[<span data-ttu-id="57489-116">Procedimiento Llamada a un servicio web de forma asincrónica</span><span class="sxs-lookup"><span data-stu-id="57489-116">How to: Call a Web Service Asynchronously</span></span>](how-to-call-a-web-service-asynchronously.md)|

## <a name="see-also"></a><span data-ttu-id="57489-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="57489-117">See also</span></span>

- [<span data-ttu-id="57489-118">My.WebServices (objeto)</span><span class="sxs-lookup"><span data-stu-id="57489-118">My.WebServices Object</span></span>](../../language-reference/objects/my-webservices-object.md)
