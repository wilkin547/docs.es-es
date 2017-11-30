---
title: Acceso a los servicios Web de aplicaciones (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Web services [Visual Basic], My.WebServices object
- My.WebServices object
- applications [Visual Basic], Web services
ms.assetid: 8ad5405b-e771-42b1-82d3-ce97af2cea9e
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f15c0fd761f08f41abc05f7019ce27bc8cf8dff3
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="accessing-application-web-services-visual-basic"></a><span data-ttu-id="ec98f-102">Acceso a los servicios Web de aplicaciones (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ec98f-102">Accessing Application Web Services (Visual Basic)</span></span>
<span data-ttu-id="ec98f-103">El objeto `My.WebServices` proporciona una instancia de cada servicio Web al que hace referencia el proyecto actual.</span><span class="sxs-lookup"><span data-stu-id="ec98f-103">The `My.WebServices` object provides an instance of each Web service referenced by the current project.</span></span> <span data-ttu-id="ec98f-104">Cada una de las instancias se crea a petición.</span><span class="sxs-lookup"><span data-stu-id="ec98f-104">Each instance is instantiated on demand.</span></span> <span data-ttu-id="ec98f-105">Puede tener acceso a estos servicios Web a través de las propiedades del objeto `My.WebServices`.</span><span class="sxs-lookup"><span data-stu-id="ec98f-105">You can access these Web services through the properties of the `My.WebServices` object.</span></span> <span data-ttu-id="ec98f-106">El nombre de la propiedad es igual que el nombre del servicio Web al que tiene acceso la propiedad.</span><span class="sxs-lookup"><span data-stu-id="ec98f-106">The name of the property is the same as the name of the Web service that the property accesses.</span></span> <span data-ttu-id="ec98f-107">Cualquier clase que hereda de <xref:System.Web.Services.Protocols.SoapHttpClientProtocol> es un servicio web.</span><span class="sxs-lookup"><span data-stu-id="ec98f-107">Any class that inherits from <xref:System.Web.Services.Protocols.SoapHttpClientProtocol> is a Web service.</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="ec98f-108">Tareas</span><span class="sxs-lookup"><span data-stu-id="ec98f-108">Tasks</span></span>  
 <span data-ttu-id="ec98f-109">La tabla siguiente muestra las posibles maneras de tener acceso a los servicios Web a los que hace referencia una aplicación.</span><span class="sxs-lookup"><span data-stu-id="ec98f-109">The following table lists possible ways to access Web services referenced by an application.</span></span>  
  
|<span data-ttu-id="ec98f-110">Para</span><span class="sxs-lookup"><span data-stu-id="ec98f-110">To</span></span>|<span data-ttu-id="ec98f-111">Vea</span><span class="sxs-lookup"><span data-stu-id="ec98f-111">See</span></span>|  
|---|---|   
|<span data-ttu-id="ec98f-112">Llamar a un servicio Web</span><span class="sxs-lookup"><span data-stu-id="ec98f-112">Call a Web service</span></span>|[<span data-ttu-id="ec98f-113">My.WebServices (objeto)</span><span class="sxs-lookup"><span data-stu-id="ec98f-113">My.WebServices Object</span></span>](../../../visual-basic/language-reference/objects/my-webservices-object.md)|  
|<span data-ttu-id="ec98f-114">Llamar de manera asincrónica a un servicio Web y controlar un evento cuando finaliza</span><span class="sxs-lookup"><span data-stu-id="ec98f-114">Call a Web service asynchronously and handle an event when it completes</span></span>|[<span data-ttu-id="ec98f-115">Llamar a un servicio web de forma asincrónica</span><span class="sxs-lookup"><span data-stu-id="ec98f-115">How to: Call a Web Service Asynchronously</span></span>](../../../visual-basic/developing-apps/programming/how-to-call-a-web-service-asynchronously.md)|  
  
## <a name="see-also"></a><span data-ttu-id="ec98f-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="ec98f-116">See Also</span></span>  
 [<span data-ttu-id="ec98f-117">My.WebServices (objeto)</span><span class="sxs-lookup"><span data-stu-id="ec98f-117">My.WebServices Object</span></span>](../../../visual-basic/language-reference/objects/my-webservices-object.md)
