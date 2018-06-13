---
title: Enlaces de WS-MetadataExchange
ms.date: 03/30/2017
ms.assetid: 10f8de5d-b81d-4ea7-b37e-7f2c00c39714
ms.openlocfilehash: 384e5bb05ba4263f245f6901b84e2388ea19bd73
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33488629"
---
# <a name="ws-metadataexchange-bindings"></a><span data-ttu-id="1ed3d-102">Enlaces de WS-MetadataExchange</span><span class="sxs-lookup"><span data-stu-id="1ed3d-102">WS-MetadataExchange Bindings</span></span>
<span data-ttu-id="1ed3d-103">En este tema se describe cómo se construyen los enlaces de intercambio de metadatos predeterminados para varios transportes.</span><span class="sxs-lookup"><span data-stu-id="1ed3d-103">This topic describes how the default metadata exchange bindings are constructed for various transports.</span></span>  
  
## <a name="the-default-bindings"></a><span data-ttu-id="1ed3d-104">Los enlaces predeterminados</span><span class="sxs-lookup"><span data-stu-id="1ed3d-104">The Default Bindings</span></span>  
  
|<span data-ttu-id="1ed3d-105">Nombre de enlace predeterminado</span><span class="sxs-lookup"><span data-stu-id="1ed3d-105">Default Binding Name</span></span>|<span data-ttu-id="1ed3d-106">Cómo se construye el enlace</span><span class="sxs-lookup"><span data-stu-id="1ed3d-106">How the binding is constructed</span></span>|  
|--------------------------|------------------------------------|  
|<span data-ttu-id="1ed3d-107">MexHttpBinding</span><span class="sxs-lookup"><span data-stu-id="1ed3d-107">MexHttpBinding</span></span>|<span data-ttu-id="1ed3d-108">Un <xref:System.ServiceModel.WSHttpBinding> con la seguridad de nivel de transporte deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="1ed3d-108">A <xref:System.ServiceModel.WSHttpBinding> with transport-level security disabled.</span></span>|  
|<span data-ttu-id="1ed3d-109">MexHttpsBinding</span><span class="sxs-lookup"><span data-stu-id="1ed3d-109">MexHttpsBinding</span></span>|<span data-ttu-id="1ed3d-110"><xref:System.ServiceModel.WSHttpBinding> que admite la seguridad de nivel de transporte.</span><span class="sxs-lookup"><span data-stu-id="1ed3d-110">A <xref:System.ServiceModel.WSHttpBinding> that supports transport-level security.</span></span>|  
|<span data-ttu-id="1ed3d-111">MexNamedPipeBinding</span><span class="sxs-lookup"><span data-stu-id="1ed3d-111">MexNamedPipeBinding</span></span>|<span data-ttu-id="1ed3d-112"><xref:System.ServiceModel.Channels.CustomBinding> con <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement> que utiliza los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="1ed3d-112">A  <xref:System.ServiceModel.Channels.CustomBinding> with a <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement> using the default values.</span></span>|  
|<span data-ttu-id="1ed3d-113">MexTcpBinding</span><span class="sxs-lookup"><span data-stu-id="1ed3d-113">MexTcpBinding</span></span>|<span data-ttu-id="1ed3d-114"><xref:System.ServiceModel.Channels.CustomBinding> con <xref:System.ServiceModel.Channels.TcpTransportBindingElement> que utiliza los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="1ed3d-114">A <xref:System.ServiceModel.Channels.CustomBinding> with a <xref:System.ServiceModel.Channels.TcpTransportBindingElement> using default values.</span></span>|
