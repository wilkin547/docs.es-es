---
title: Extensibilidad de enlaces
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cabdd583-ddf5-493e-9dba-c6c31cde8f65
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 61c8ae647012c5f1fffe5cf65c63b64cde62af1b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="binding-extensibility"></a>Extensibilidad de enlaces
Esta sección contiene ejemplos que muestran el enlace personalizado en [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].  
  
## <a name="in-this-section"></a>En esta sección  
 <xref:System.ServiceModel.NetHttpBinding>  
 Muestra cómo implementar un enlace que apila <xref:System.ServiceModel.Channels.HttpTransportBindingElement> o <xref:System.ServiceModel.Channels.HttpsTransportBindingElement> encima de <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>.  
  
 <!--zz <xref:System.ServiceModel.WSStreamedHttpBinding> --> `System.ServiceModel.WSStreamedHttpBinding` 
 Muestra cómo crear un enlace diseñado para admitir escenarios de transmisión por secuencias cuando se usa el transporte HTTP.
