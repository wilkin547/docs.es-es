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
ms.workload: dotnet
ms.openlocfilehash: 8d305f3bf34b3b14da566fa792552e24e695ef33
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ws-metadataexchange-bindings"></a>Enlaces de WS-MetadataExchange
En este tema se describe cómo se construyen los enlaces de intercambio de metadatos predeterminados para varios transportes.  
  
## <a name="the-default-bindings"></a>Los enlaces predeterminados  
  
|Nombre de enlace predeterminado|Cómo se construye el enlace|  
|--------------------------|------------------------------------|  
|MexHttpBinding|Un <xref:System.ServiceModel.WSHttpBinding> con la seguridad de nivel de transporte deshabilitada.|  
|MexHttpsBinding|<xref:System.ServiceModel.WSHttpBinding> que admite la seguridad de nivel de transporte.|  
|MexNamedPipeBinding|<xref:System.ServiceModel.Channels.CustomBinding> con <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement> que utiliza los valores predeterminados.|  
|MexTcpBinding|<xref:System.ServiceModel.Channels.CustomBinding> con <xref:System.ServiceModel.Channels.TcpTransportBindingElement> que utiliza los valores predeterminados.|
