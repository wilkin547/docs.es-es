---
description: 'Más información acerca de: comunicaciones básicas: compatibilidad con webhost'
title: 'Comunicaciones básicas: compatibilidad de Webhost'
ms.date: 03/30/2017
ms.assetid: 034c501f-96f9-4ef7-9602-3ac21788fd3e
ms.openlocfilehash: c132527caf4d08b7423ff8af9442ca609d4e645f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99686523"
---
# <a name="core-communications-webhost-support"></a>Comunicaciones básicas: compatibilidad de Webhost

En este tema se muestran todas las excepciones generadas por la compatibilidad de Webhost.

## <a name="exception-list"></a>Lista de excepciones

|Código de recurso|Cadena de recurso|
|-------------------|---------------------|
|Hosting_CompatibilityServiceNotHosted|Este servicio requiere compatibilidad con ASP.NET. También se debe hospedar en IIS. Hospede el servicio en IIS con la compatibilidad de ASP.NET activada en Web.config o establezca la propiedad AspNetCompatibilityRequirementsAttribute.AspNetCompatibilityRequirementsMode en un valor distinto de Requerido.|
|Hosting_ListenerNotFoundForActivationInRecycling|Ningún canal está realizando escuchas activamente en la dirección especificada. Si se está reciclando una aplicación, se cerrará el servicio.|
|Hosting_NonHTTPInCompatibilityMode|Los únicos protocolos que se admiten con la compatibilidad de ASP.NET son HTTP y HTTPS. Quite el extremo especificado o deshabilite la compatibilidad de ASP.NET para la aplicación.|
|Hosting_ProcessNotExecutingUnderHostedContext|No se puede invocar el proceso de hospedaje especificado dentro del entorno de hospedaje actual. Esta API requiere que la aplicación que realiza la llamada se hospede en Internet Information Services o en el Servicio de activación de procesos de Windows.|
|Hosting_ServiceCompatibilityRequire|No se puede activar el servicio porque requiere la compatibilidad de ASP.NET. La compatibilidad de ASP.NET no está habilitada para esta aplicación. Habilite la compatibilidad de ASP.NET en archivo Web.config o establezca AspNetCompatibilityRequirementsAttribute.AspNetCompatibility.|
