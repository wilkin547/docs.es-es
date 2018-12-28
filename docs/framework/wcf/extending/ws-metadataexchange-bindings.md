---
title: Enlaces de WS-MetadataExchange
ms.date: 03/30/2017
ms.assetid: 10f8de5d-b81d-4ea7-b37e-7f2c00c39714
ms.openlocfilehash: 03e6e6d5ee7e69b397acd0f51b8037f02c1804ec
ms.sourcegitcommit: 0888d7b24f475c346a3f444de8d83ec1ca7cd234
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2018
ms.locfileid: "53767353"
---
# <a name="ws-metadataexchange-bindings"></a><span data-ttu-id="de961-102">Enlaces de WS-MetadataExchange</span><span class="sxs-lookup"><span data-stu-id="de961-102">WS-MetadataExchange Bindings</span></span>
<span data-ttu-id="de961-103">En este tema se describe cómo se construyen los enlaces de intercambio de metadatos predeterminados para varios transportes.</span><span class="sxs-lookup"><span data-stu-id="de961-103">This topic describes how the default metadata exchange bindings are constructed for various transports.</span></span>  
  
## <a name="the-default-bindings"></a><span data-ttu-id="de961-104">Los enlaces predeterminados</span><span class="sxs-lookup"><span data-stu-id="de961-104">The Default Bindings</span></span>  
  
|<span data-ttu-id="de961-105">Nombre de enlace predeterminado</span><span class="sxs-lookup"><span data-stu-id="de961-105">Default Binding Name</span></span>|<span data-ttu-id="de961-106">Cómo se construye el enlace</span><span class="sxs-lookup"><span data-stu-id="de961-106">How the binding is constructed</span></span>|  
|--------------------------|------------------------------------|  
|<span data-ttu-id="de961-107">mexHttpBinding</span><span class="sxs-lookup"><span data-stu-id="de961-107">mexHttpBinding</span></span>|<span data-ttu-id="de961-108">Un <xref:System.ServiceModel.WSHttpBinding> con la seguridad de nivel de transporte deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="de961-108">A <xref:System.ServiceModel.WSHttpBinding> with transport-level security disabled.</span></span>|  
|<span data-ttu-id="de961-109">mexHttpsBinding</span><span class="sxs-lookup"><span data-stu-id="de961-109">mexHttpsBinding</span></span>|<span data-ttu-id="de961-110"><xref:System.ServiceModel.WSHttpBinding> que admite la seguridad de nivel de transporte.</span><span class="sxs-lookup"><span data-stu-id="de961-110">A <xref:System.ServiceModel.WSHttpBinding> that supports transport-level security.</span></span>|  
|<span data-ttu-id="de961-111">mexNamedPipeBinding</span><span class="sxs-lookup"><span data-stu-id="de961-111">mexNamedPipeBinding</span></span>|<span data-ttu-id="de961-112"><xref:System.ServiceModel.Channels.CustomBinding> con <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement> que utiliza los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="de961-112">A  <xref:System.ServiceModel.Channels.CustomBinding> with a <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement> using the default values.</span></span>|  
|<span data-ttu-id="de961-113">mexTcpBinding</span><span class="sxs-lookup"><span data-stu-id="de961-113">mexTcpBinding</span></span>|<span data-ttu-id="de961-114"><xref:System.ServiceModel.Channels.CustomBinding> con <xref:System.ServiceModel.Channels.TcpTransportBindingElement> que utiliza los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="de961-114">A <xref:System.ServiceModel.Channels.CustomBinding> with a <xref:System.ServiceModel.Channels.TcpTransportBindingElement> using default values.</span></span>|
