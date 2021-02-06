---
description: 'Más información acerca de: enlaces de WS-MetadataExchange'
title: Enlaces de WS-MetadataExchange
ms.date: 03/30/2017
ms.assetid: 10f8de5d-b81d-4ea7-b37e-7f2c00c39714
ms.openlocfilehash: 3bcea573ad436a85285fab5657e58defa9113d9c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99643948"
---
# <a name="ws-metadataexchange-bindings"></a><span data-ttu-id="05996-103">Enlaces de WS-MetadataExchange</span><span class="sxs-lookup"><span data-stu-id="05996-103">WS-MetadataExchange Bindings</span></span>

<span data-ttu-id="05996-104">En este tema se describe cómo se construyen los enlaces de intercambio de metadatos predeterminados para varios transportes.</span><span class="sxs-lookup"><span data-stu-id="05996-104">This topic describes how the default metadata exchange bindings are constructed for various transports.</span></span>  
  
## <a name="the-default-bindings"></a><span data-ttu-id="05996-105">Los enlaces predeterminados</span><span class="sxs-lookup"><span data-stu-id="05996-105">The Default Bindings</span></span>  
  
|<span data-ttu-id="05996-106">Nombre de enlace predeterminado</span><span class="sxs-lookup"><span data-stu-id="05996-106">Default Binding Name</span></span>|<span data-ttu-id="05996-107">Cómo se construye el enlace</span><span class="sxs-lookup"><span data-stu-id="05996-107">How the binding is constructed</span></span>|  
|--------------------------|------------------------------------|  
|<span data-ttu-id="05996-108">mexHttpBinding</span><span class="sxs-lookup"><span data-stu-id="05996-108">mexHttpBinding</span></span>|<span data-ttu-id="05996-109">Un <xref:System.ServiceModel.WSHttpBinding> con la seguridad de nivel de transporte deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="05996-109">A <xref:System.ServiceModel.WSHttpBinding> with transport-level security disabled.</span></span>|  
|<span data-ttu-id="05996-110">mexHttpsBinding</span><span class="sxs-lookup"><span data-stu-id="05996-110">mexHttpsBinding</span></span>|<span data-ttu-id="05996-111"><xref:System.ServiceModel.WSHttpBinding> que admite la seguridad de nivel de transporte.</span><span class="sxs-lookup"><span data-stu-id="05996-111">A <xref:System.ServiceModel.WSHttpBinding> that supports transport-level security.</span></span>|  
|<span data-ttu-id="05996-112">mexNamedPipeBinding</span><span class="sxs-lookup"><span data-stu-id="05996-112">mexNamedPipeBinding</span></span>|<span data-ttu-id="05996-113"><xref:System.ServiceModel.Channels.CustomBinding> con <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement> que utiliza los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="05996-113">A  <xref:System.ServiceModel.Channels.CustomBinding> with a <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement> using the default values.</span></span>|  
|<span data-ttu-id="05996-114">mexTcpBinding</span><span class="sxs-lookup"><span data-stu-id="05996-114">mexTcpBinding</span></span>|<span data-ttu-id="05996-115"><xref:System.ServiceModel.Channels.CustomBinding> con <xref:System.ServiceModel.Channels.TcpTransportBindingElement> que utiliza los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="05996-115">A <xref:System.ServiceModel.Channels.CustomBinding> with a <xref:System.ServiceModel.Channels.TcpTransportBindingElement> using default values.</span></span>|
