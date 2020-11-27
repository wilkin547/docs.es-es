---
title: Enlaces de WS-MetadataExchange
ms.date: 03/30/2017
ms.assetid: 10f8de5d-b81d-4ea7-b37e-7f2c00c39714
ms.openlocfilehash: 94f0ba602cd1f58f5491a44a64e24be8ea52895b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96293993"
---
# <a name="ws-metadataexchange-bindings"></a><span data-ttu-id="1fe7a-102">Enlaces de WS-MetadataExchange</span><span class="sxs-lookup"><span data-stu-id="1fe7a-102">WS-MetadataExchange Bindings</span></span>

<span data-ttu-id="1fe7a-103">En este tema se describe cómo se construyen los enlaces de intercambio de metadatos predeterminados para varios transportes.</span><span class="sxs-lookup"><span data-stu-id="1fe7a-103">This topic describes how the default metadata exchange bindings are constructed for various transports.</span></span>  
  
## <a name="the-default-bindings"></a><span data-ttu-id="1fe7a-104">Los enlaces predeterminados</span><span class="sxs-lookup"><span data-stu-id="1fe7a-104">The Default Bindings</span></span>  
  
|<span data-ttu-id="1fe7a-105">Nombre de enlace predeterminado</span><span class="sxs-lookup"><span data-stu-id="1fe7a-105">Default Binding Name</span></span>|<span data-ttu-id="1fe7a-106">Cómo se construye el enlace</span><span class="sxs-lookup"><span data-stu-id="1fe7a-106">How the binding is constructed</span></span>|  
|--------------------------|------------------------------------|  
|<span data-ttu-id="1fe7a-107">mexHttpBinding</span><span class="sxs-lookup"><span data-stu-id="1fe7a-107">mexHttpBinding</span></span>|<span data-ttu-id="1fe7a-108">Un <xref:System.ServiceModel.WSHttpBinding> con la seguridad de nivel de transporte deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="1fe7a-108">A <xref:System.ServiceModel.WSHttpBinding> with transport-level security disabled.</span></span>|  
|<span data-ttu-id="1fe7a-109">mexHttpsBinding</span><span class="sxs-lookup"><span data-stu-id="1fe7a-109">mexHttpsBinding</span></span>|<span data-ttu-id="1fe7a-110"><xref:System.ServiceModel.WSHttpBinding> que admite la seguridad de nivel de transporte.</span><span class="sxs-lookup"><span data-stu-id="1fe7a-110">A <xref:System.ServiceModel.WSHttpBinding> that supports transport-level security.</span></span>|  
|<span data-ttu-id="1fe7a-111">mexNamedPipeBinding</span><span class="sxs-lookup"><span data-stu-id="1fe7a-111">mexNamedPipeBinding</span></span>|<span data-ttu-id="1fe7a-112"><xref:System.ServiceModel.Channels.CustomBinding> con <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement> que utiliza los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="1fe7a-112">A  <xref:System.ServiceModel.Channels.CustomBinding> with a <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement> using the default values.</span></span>|  
|<span data-ttu-id="1fe7a-113">mexTcpBinding</span><span class="sxs-lookup"><span data-stu-id="1fe7a-113">mexTcpBinding</span></span>|<span data-ttu-id="1fe7a-114"><xref:System.ServiceModel.Channels.CustomBinding> con <xref:System.ServiceModel.Channels.TcpTransportBindingElement> que utiliza los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="1fe7a-114">A <xref:System.ServiceModel.Channels.CustomBinding> with a <xref:System.ServiceModel.Channels.TcpTransportBindingElement> using default values.</span></span>|
