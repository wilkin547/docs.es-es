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
# <a name="ws-metadataexchange-bindings"></a>Enlaces de WS-MetadataExchange
En este tema se describe cómo se construyen los enlaces de intercambio de metadatos predeterminados para varios transportes.  
  
## <a name="the-default-bindings"></a>Los enlaces predeterminados  
  
|Nombre de enlace predeterminado|Cómo se construye el enlace|  
|--------------------------|------------------------------------|  
|mexHttpBinding|Un <xref:System.ServiceModel.WSHttpBinding> con la seguridad de nivel de transporte deshabilitada.|  
|mexHttpsBinding|<xref:System.ServiceModel.WSHttpBinding> que admite la seguridad de nivel de transporte.|  
|mexNamedPipeBinding|<xref:System.ServiceModel.Channels.CustomBinding> con <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement> que utiliza los valores predeterminados.|  
|mexTcpBinding|<xref:System.ServiceModel.Channels.CustomBinding> con <xref:System.ServiceModel.Channels.TcpTransportBindingElement> que utiliza los valores predeterminados.|
