---
title: Enlaces de WS-MetadataExchange
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 10f8de5d-b81d-4ea7-b37e-7f2c00c39714
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a7267fa8e71a7bbe202bce9897ea09079307be50
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="ws-metadataexchange-bindings"></a><span data-ttu-id="fbc4b-102">Enlaces de WS-MetadataExchange</span><span class="sxs-lookup"><span data-stu-id="fbc4b-102">WS-MetadataExchange Bindings</span></span>
<span data-ttu-id="fbc4b-103">En este tema se describe cómo se construyen los enlaces de intercambio de metadatos predeterminados para varios transportes.</span><span class="sxs-lookup"><span data-stu-id="fbc4b-103">This topic describes how the default metadata exchange bindings are constructed for various transports.</span></span>  
  
## <a name="the-default-bindings"></a><span data-ttu-id="fbc4b-104">Los enlaces predeterminados</span><span class="sxs-lookup"><span data-stu-id="fbc4b-104">The Default Bindings</span></span>  
  
|<span data-ttu-id="fbc4b-105">Nombre de enlace predeterminado</span><span class="sxs-lookup"><span data-stu-id="fbc4b-105">Default Binding Name</span></span>|<span data-ttu-id="fbc4b-106">Cómo se construye el enlace</span><span class="sxs-lookup"><span data-stu-id="fbc4b-106">How the binding is constructed</span></span>|  
|--------------------------|------------------------------------|  
|<span data-ttu-id="fbc4b-107">MexHttpBinding</span><span class="sxs-lookup"><span data-stu-id="fbc4b-107">MexHttpBinding</span></span>|<span data-ttu-id="fbc4b-108">Un <xref:System.ServiceModel.WSHttpBinding> con la seguridad de nivel de transporte deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="fbc4b-108">A <xref:System.ServiceModel.WSHttpBinding> with transport-level security disabled.</span></span>|  
|<span data-ttu-id="fbc4b-109">MexHttpsBinding</span><span class="sxs-lookup"><span data-stu-id="fbc4b-109">MexHttpsBinding</span></span>|<span data-ttu-id="fbc4b-110"><xref:System.ServiceModel.WSHttpBinding> que admite la seguridad de nivel de transporte.</span><span class="sxs-lookup"><span data-stu-id="fbc4b-110">A <xref:System.ServiceModel.WSHttpBinding> that supports transport-level security.</span></span>|  
|<span data-ttu-id="fbc4b-111">MexNamedPipeBinding</span><span class="sxs-lookup"><span data-stu-id="fbc4b-111">MexNamedPipeBinding</span></span>|<span data-ttu-id="fbc4b-112"><xref:System.ServiceModel.Channels.CustomBinding> con <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement> que utiliza los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="fbc4b-112">A  <xref:System.ServiceModel.Channels.CustomBinding> with a <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement> using the default values.</span></span>|  
|<span data-ttu-id="fbc4b-113">MexTcpBinding</span><span class="sxs-lookup"><span data-stu-id="fbc4b-113">MexTcpBinding</span></span>|<span data-ttu-id="fbc4b-114"><xref:System.ServiceModel.Channels.CustomBinding> con <xref:System.ServiceModel.Channels.TcpTransportBindingElement> que utiliza los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="fbc4b-114">A <xref:System.ServiceModel.Channels.CustomBinding> with a <xref:System.ServiceModel.Channels.TcpTransportBindingElement> using default values.</span></span>|
