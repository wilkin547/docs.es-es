---
description: 'Más información acerca de: 207-FaultProviderInvoked'
title: 207 - FaultProviderInvoked
ms.date: 03/30/2017
ms.assetid: b730d903-01c2-4deb-85a4-da12f8a21fe4
ms.openlocfilehash: 03c4f1669fc61019ccf4d23d2994f136e231fbec
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99728072"
---
# <a name="207---faultproviderinvoked"></a>207 - FaultProviderInvoked

## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|Id.|207|  
|Palabras clave|Troubleshooting, ServiceModel|  
|Nivel|Información|  
|Canal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Descripción  

 Este evento se emite una vez invocado `FaultProvider`.  
  
## <a name="message"></a>Message  

 El distribuidor invocó un FaultProvider del tipo '%1' con una excepción del tipo '%2'.  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|TypeName|`xs:string`|Nombre completo (FullName) de CLR del tipo del `FaultProvider` invocado.|  
|ExceptionTypeName|`xs:string`|El nombre completo (FullName) de CLR de la excepción en la que ha funcionado `FaultProvider`.|  
|HostReference|`xs:string`|En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web. Su formato se define como ' ruta de acceso virtual de la aplicación de nombre de sitio web&#124;ruta de acceso virtual del servicio&#124;ServiceName '. Ejemplo: ' sitio web predeterminado/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.|  
|AppDomain|`xs:string`|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
