---
description: 'Más información acerca de: Acceso a los servicios Web de aplicaciones (Visual Basic)'
title: Acceso a los servicios web de las aplicaciones
ms.date: 07/20/2015
helpviewer_keywords:
- Web services [Visual Basic], My.WebServices object
- My.WebServices object
- applications [Visual Basic], Web services
ms.assetid: 8ad5405b-e771-42b1-82d3-ce97af2cea9e
ms.openlocfilehash: 4efd35ed7c8f4251a749b85a45242af299a51e6c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797892"
---
# <a name="accessing-application-web-services-visual-basic"></a>Acceso a los servicios Web de aplicaciones (Visual Basic)

El objeto `My.WebServices` proporciona una instancia de cada servicio Web al que hace referencia el proyecto actual. Cada una de las instancias se crea a petición. Puede tener acceso a estos servicios Web a través de las propiedades del objeto `My.WebServices`. El nombre de la propiedad es igual que el nombre del servicio Web al que tiene acceso la propiedad. Cualquier clase que hereda de <xref:System.Web.Services.Protocols.SoapHttpClientProtocol> es un servicio web.

## <a name="tasks"></a>Tareas

La tabla siguiente muestra las posibles maneras de tener acceso a los servicios Web a los que hace referencia una aplicación.

|En|Vea|
|---|---|
|Llamar a un servicio Web|[My.WebServices (objeto)](../../language-reference/objects/my-webservices-object.md)|
|Llamar de manera asincrónica a un servicio Web y controlar un evento cuando finaliza|[Procedimiento Llamada a un servicio web de forma asincrónica](how-to-call-a-web-service-asynchronously.md)|

## <a name="see-also"></a>Vea también

- [My.WebServices (objeto)](../../language-reference/objects/my-webservices-object.md)
