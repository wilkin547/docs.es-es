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
# <a name="ws-metadataexchange-bindings"></a>Enlaces de WS-MetadataExchange

En este tema se describe cómo se construyen los enlaces de intercambio de metadatos predeterminados para varios transportes.  
  
## <a name="the-default-bindings"></a>Los enlaces predeterminados  
  
|Nombre de enlace predeterminado|Cómo se construye el enlace|  
|--------------------------|------------------------------------|  
|mexHttpBinding|Un <xref:System.ServiceModel.WSHttpBinding> con la seguridad de nivel de transporte deshabilitada.|  
|mexHttpsBinding|<xref:System.ServiceModel.WSHttpBinding> que admite la seguridad de nivel de transporte.|  
|mexNamedPipeBinding|<xref:System.ServiceModel.Channels.CustomBinding> con <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement> que utiliza los valores predeterminados.|  
|mexTcpBinding|<xref:System.ServiceModel.Channels.CustomBinding> con <xref:System.ServiceModel.Channels.TcpTransportBindingElement> que utiliza los valores predeterminados.|
