---
title: Aplicaciones SOA
description: Ciclo de vida de aplicaciones de Docker en contenedor con la plataforma y las herramientas de Microsoft
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: 7f88daaf0787cf780e7ab9602f35ae4e6ab8308c
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53155319"
---
# <a name="soa-applications"></a>Aplicaciones SOA

SOA era un término sobreutilizado y significaba tantas cosas diferentes para diferentes personas. Pero como mínimo y como denominador común, SOA, o la orientación al servicio, Media de esa estructura la arquitectura de la aplicación descomponiéndola en varios servicios (normalmente como servicios HTTP) que se pueden clasificar en diferentes tipos, como subsistemas o bien, en otros casos, como capas.

Hoy en día, puede implementar estos servicios como contenedores de Docker, que soluciona problemas relacionados con la implementación, ya que todas las dependencias se incluyen dentro de la imagen de contenedor. Sin embargo, cuando necesite escalar horizontalmente SOA, pueden surgir desafíos si está implementando en función de instancias únicas. Esto es donde Docker software de clústeres o orchestrator le ayudará. Veremos esto más detalladamente en la sección siguiente cuando se examinan los enfoques de microservicios.

Al final del día, las soluciones de agrupación en clústeres de contenedor son útiles para ambas una arquitectura tradicional de SOA o para una arquitectura de microservicios más avanzada en la que cada microservicio posee su modelo de datos. Además, gracias a varias bases de datos, también puede escalar horizontalmente la capa de datos en lugar de trabajar con bases de datos monolíticas compartidas por los servicios SOA. Sin embargo, la discusión sobre cómo dividir los datos es puramente sobre arquitectura y diseño.

>[!div class="step-by-step"]
>[Anterior](state-and-data-in-docker-applications.md)
>[Siguiente](orchestrate-high-scalability-availability.md)