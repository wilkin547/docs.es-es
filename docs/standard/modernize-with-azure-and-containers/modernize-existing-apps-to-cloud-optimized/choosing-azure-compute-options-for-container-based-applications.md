---
title: Elegir plataformas de proceso de Azure para aplicaciones basadas en el contenedor
description: Modernizar las aplicaciones .NET existentes con contenedores de Windows y de nube de Azure | Elegir plataformas de proceso de Azure para aplicaciones basadas en el contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/04/2018
ms.openlocfilehash: ebf022a52aaaf95ae335976f5e097921b0ac8006
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/10/2018
ms.locfileid: "33958015"
---
# <a name="choosing-azure-compute-platforms-for-container-based-applications"></a>Elegir plataformas de proceso de Azure para aplicaciones basadas en el contenedor

Como es posible que haya observado después de leer las secciones anteriores, Azure es una nube abierta que ofrece varias opciones. Puede usar el ajuste óptimo para sus necesidades, sin embargo, también expone preguntas acerca de los productos y tecnologías que se debe usar para las aplicaciones en contenedores.

Como un *de forma predeterminada* recomendación, éste es el criterio principal recomendado en esta guía:

  - **Única aplicación monolítico:** elegir servicio de aplicaciones de Azure
  - **Aplicación de N niveles:** elija orchestrators como servicio de Kubernetes de Azure (AKS), servicio tejido (SF) o servicio de aplicaciones si tiene un único o algunos servicios back-end
  - **Linux microservicios:** AKS/Kubernetes elija
  - **Windows microservicios:** elija Service Fabric
  - **Funciones sin servidor & controladores de eventos:** elegir funciones de Azure
  - **Proceso por lotes a gran escala:** elija Azure Batch

Sin embargo, esta recomendación debe tener cuidada con un gesto de valor "salt", como la selección del producto dependerá de las necesidades y las características de la aplicación específica. No todas las aplicaciones son los mismos, incluso cuando inicialmente pueden parecer tipos similares.

Después de realizar un análisis más profundos de necesidades de la aplicación, puede variar el producto seleccionado. Pero, como punto de partida, es conveniente tener instrucciones inicial desde donde puede empezar a evaluar y probar basado en prioridad concreta.

En la ilustración siguiente, puede analizar más global mientras la tabla de decisiones detallada.

![](./media/image8.5.png)

Observe cómo el subyacente OS (frente a Windows. Linux) también puede ser un factor de decisión como algunos orchestrators son más maduro en contenedores de Linux y otros en los contenedores de Windows. Por ejemplo, los contenedores de Linux están muy consolidados en Kubernetes (AKS en Azure) pero menos maduro en el tejido de servicio. Por otro lado, los contenedores de Windows son más maduro en Service Fabric (que se publicó en mayo de 2017) y menos maduro en AKS.

Sin embargo, pierden esas diferencias en el nivel de madurez de sistema operativo en el futuro y varias plataformas tendrán el nivel de madurez de comparable OS y la decisión de disposición de más información sobre las preferencias en función de las características específicas que la aplicación necesite o, según el ecosistema de cada plataforma motivos.


>[!div class="step-by-step"]
[Anterior](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
[Siguiente](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)
