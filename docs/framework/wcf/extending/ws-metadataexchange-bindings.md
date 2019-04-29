---
title: Enlaces de WS-MetadataExchange
ms.date: 03/30/2017
ms.assetid: 10f8de5d-b81d-4ea7-b37e-7f2c00c39714
ms.openlocfilehash: 03e6e6d5ee7e69b397acd0f51b8037f02c1804ec
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61795482"
---
# <a name="ws-metadataexchange-bindings"></a><span data-ttu-id="a760b-102">Enlaces de WS-MetadataExchange</span><span class="sxs-lookup"><span data-stu-id="a760b-102">WS-MetadataExchange Bindings</span></span>
<span data-ttu-id="a760b-103">En este tema se describe cómo se construyen los enlaces de intercambio de metadatos predeterminados para varios transportes.</span><span class="sxs-lookup"><span data-stu-id="a760b-103">This topic describes how the default metadata exchange bindings are constructed for various transports.</span></span>  
  
## <a name="the-default-bindings"></a><span data-ttu-id="a760b-104">Los enlaces predeterminados</span><span class="sxs-lookup"><span data-stu-id="a760b-104">The Default Bindings</span></span>  
  
|<span data-ttu-id="a760b-105">Nombre de enlace predeterminado</span><span class="sxs-lookup"><span data-stu-id="a760b-105">Default Binding Name</span></span>|<span data-ttu-id="a760b-106">Cómo se construye el enlace</span><span class="sxs-lookup"><span data-stu-id="a760b-106">How the binding is constructed</span></span>|  
|--------------------------|------------------------------------|  
|<span data-ttu-id="a760b-107">mexHttpBinding</span><span class="sxs-lookup"><span data-stu-id="a760b-107">mexHttpBinding</span></span>|<span data-ttu-id="a760b-108">Un <xref:System.ServiceModel.WSHttpBinding> con la seguridad de nivel de transporte deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="a760b-108">A <xref:System.ServiceModel.WSHttpBinding> with transport-level security disabled.</span></span>|  
|<span data-ttu-id="a760b-109">mexHttpsBinding</span><span class="sxs-lookup"><span data-stu-id="a760b-109">mexHttpsBinding</span></span>|<span data-ttu-id="a760b-110"><xref:System.ServiceModel.WSHttpBinding> que admite la seguridad de nivel de transporte.</span><span class="sxs-lookup"><span data-stu-id="a760b-110">A <xref:System.ServiceModel.WSHttpBinding> that supports transport-level security.</span></span>|  
|<span data-ttu-id="a760b-111">mexNamedPipeBinding</span><span class="sxs-lookup"><span data-stu-id="a760b-111">mexNamedPipeBinding</span></span>|<span data-ttu-id="a760b-112"><xref:System.ServiceModel.Channels.CustomBinding> con <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement> que utiliza los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="a760b-112">A  <xref:System.ServiceModel.Channels.CustomBinding> with a <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement> using the default values.</span></span>|  
|<span data-ttu-id="a760b-113">mexTcpBinding</span><span class="sxs-lookup"><span data-stu-id="a760b-113">mexTcpBinding</span></span>|<span data-ttu-id="a760b-114"><xref:System.ServiceModel.Channels.CustomBinding> con <xref:System.ServiceModel.Channels.TcpTransportBindingElement> que utiliza los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="a760b-114">A <xref:System.ServiceModel.Channels.CustomBinding> with a <xref:System.ServiceModel.Channels.TcpTransportBindingElement> using default values.</span></span>|
