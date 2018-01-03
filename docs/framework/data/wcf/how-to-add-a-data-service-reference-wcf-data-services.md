---
title: "Cómo: Agregar una referencia a Data Services (Data Services de WCF)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: WCF Data Services, configuring
ms.assetid: 62c6f318-3ee1-433a-b7a3-efa234c3034c
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1fa20e9ed0cefbe587bba90ad25d5460592e3ecf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-a-data-service-reference-wcf-data-services"></a>Cómo: Agregar una referencia a Data Services (Data Services de WCF)
Puede usar el **Agregar referencia de servicio** cuadro de diálogo de Visual Studio para agregar una referencia a [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]. Esto le permite tener acceso más fácilmente a un servicio de datos en una aplicación cliente desarrollada en Visual Studio. Cuando complete este procedimiento, se generarán clases de datos basadas en los metadatos que se obtienen del servicio de datos. Para obtener más información, consulte [generar la biblioteca de cliente de servicio de datos](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md).  
  
### <a name="to-add-a-data-service-reference"></a>Para agregar una referencia a un servicio de datos  
  
1.  (Opcional) Si el servicio de datos no forma parte de la solución y no se está ejecutando, inícielo y anote el URI del mismo.  
  
2.  Haga clic en el proyecto de cliente y, a continuación, seleccione **Agregar referencia de servicio**.  
  
3.  Si el servicio de datos forma parte de la solución actual, haga clic en **Discover**.  
  
     O bien  
  
     En el **dirección** cuadro de texto, escriba la dirección URL base del servicio de datos, como `http://localhost:1234/Northwind.svc`y, a continuación, haga clic en **vaya**.  
  
4.  Haga clic en **Aceptar**.  
  
     De este modo se agrega un nuevo archivo de código que contiene las clases de datos que se usan para obtener acceso e interactuar con los recursos del servicio de datos como objetos.  
  
## <a name="see-also"></a>Vea también  
 [Inicio rápido](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)
