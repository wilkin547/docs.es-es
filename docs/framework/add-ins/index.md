---
title: Complementos y extensibilidad
ms.date: 03/30/2017
helpviewer_keywords:
- extensibility [.NET Framework], add-ins
- add-ins [.NET Framework]
- add-ins [.NET Framework], about
- hosts [.NET Framework], compared to add-ins
- .NET Framework, add-ins
- add-in pipeline [.NET Framework], about
- add-ins [.NET Framework], compared to hosts
- .NET Framework, extensibility
- versioning [.NET Framework], add-ins
ms.assetid: 8dd45b02-7218-40f9-857d-40d7b98b850b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eb2485f2ecf0426360dba80d443500a92b5a7af6
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43510059"
---
# <a name="add-ins-and-extensibility"></a>Complementos y extensibilidad
<a name="top"></a> Los complementos ofrecen características o servicios extendidos para una aplicación host. El [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] proporciona un modelo de programación que los desarrolladores pueden usar para desarrollar complementos y activarlos en la aplicación host. Para ello, el modelo construye una canalización de comunicación entre el host y el complemento. El modelo se implementa con los tipos de los espacios de nombres <xref:System.AddIn>, <xref:System.AddIn.Hosting>, <xref:System.AddIn.Pipeline>y <xref:System.AddIn.Contract> .  
  
 Esta información general contiene las siguientes secciones:  
  
-   [Modelo de complementos](#addin_model)  
  
-   [Distinción entre complementos y hosts](#distinguishing_between_addins_and_hosts)  
  
-   [Temas relacionados](#related_topics)  
  
-   [Referencia](#reference)  
  
> [!NOTE]
>  Puede encontrar código de ejemplo adicional y vistas previas de tecnología de cliente de herramientas para compilar canalizaciones, en el [sitio Managed Extensibility and Add-In Framework de CodePlex](https://go.microsoft.com/fwlink/?LinkId=121190).  
  
<a name="addin_model"></a>   
## <a name="add-in-model"></a>Modelo de complementos  
 El modelo de complementos está formado por una serie de segmentos que constituyen la canalización de complementos (también llamada “canalización de comunicación”), responsable de toda la comunicación entre el complemento y el host. La canalización es un modelo de comunicación simétrico de segmentos que intercambian datos entre un complemento y su host. Al desarrollar estos segmentos entre el host y el complemento, proporciona los niveles de abstracción necesarios para admitir el control de versiones y el aislamiento del complemento.  
  
 La ilustración siguiente muestra la canalización.  
  
 ![Agregar&#45;en el modelo de canalización. ](../../../docs/framework/add-ins/media/addin1.png "AddIn1")  
Canalización de complementos  
  
 No es necesario que los ensamblados de estos segmentos estén en el mismo dominio de aplicación. Puede cargar un complemento en su propio dominio de aplicación nuevo, en un dominio de aplicación existente o, incluso, en el dominio de aplicación del host. Puede cargar varios complementos en el mismo dominio de aplicación, lo que permite a los complementos compartir recursos y contextos de seguridad.  
  
 El modelo de complementos admite, y recomienda, un límite opcional entre el host y el complemento, que se denomina “límite de aislamiento” (también llamado “límite de comunicación remota”). Este límite puede ser un límite de proceso o un dominio de aplicación.  
  
 El segmento de contrato situado en el centro de la canalización se carga en el dominio de aplicación del host y el dominio de aplicación del complemento. El contrato define los métodos virtuales que utilizan el host y el complemento para intercambiar tipos entre sí.  
  
 Para pasar a través del límite de aislamiento, los tipos deben ser contratos o tipos serializables. Los segmentos de adaptador de la canalización deben convertir en contratos los tipos que no son contratos ni tipos serializables.  
  
 Los segmentos de vista de la canalización son interfaces o clases base abstractas que proporcionan al host y al complemento una vista de los métodos que comparten, como se define en el contrato.  
  
 Para obtener más información sobre cómo desarrollar segmentos de canalización, consulte [Pipeline Development](../../../docs/framework/add-ins/pipeline-development.md).  
  
 Las secciones siguientes describen las características del modelo de complementos.  
  
### <a name="independent-versioning"></a>Control de versiones independiente  
 El modelo de complementos permite controlar de manera independiente las versiones de los hosts y los complementos. En consecuencia, el modelo de complementos habilita los escenarios siguientes:  
  
-   Creación de un adaptador que permite a un host utilizar un complemento compilado para una versión anterior del host.  
  
-   Creación de un adaptador que permite a un host utilizar un complemento compilado para una versión posterior del host.  
  
-   Creación de un adaptador que permite a un host utilizar complementos compilados para otro host.  
  
### <a name="discovery-and-activation"></a>Detección y activación  
 Puede activar un complemento con un token de una colección que representa a los complementos encontrados en un almacén de información. Los complementos se encuentran buscando el tipo que define la vista del host del complemento. También puede buscar un complemento específico por el tipo que define al complemento. El almacén de información se compone de dos archivos caché: el almacén de canalizaciones y el almacén de complementos.  
  
 Para obtener información sobre cómo actualizar y volver a generar el almacén de información, consulte [detección de complementos](https://msdn.microsoft.com/library/5d268dde-11df-4c4d-a022-f58d88bbc421). Para obtener información sobre la activación de complementos, consulte [activación de complementos](https://msdn.microsoft.com/library/bedcbcdf-5964-4215-b5f3-3299798b2b3f) y [Cómo: activar complementos con diferente seguridad y aislamiento](https://msdn.microsoft.com/library/7afe7ec8-5158-4350-9119-5df0ecab8aa5).  
  
### <a name="isolation-levels-and-external-processes"></a>Niveles de aislamiento y procesos externos  
 El modelo de complementos admite varios niveles de aislamiento entre un complemento y su host o entre diferentes complementos. Empezando por el menos aislado, los niveles son los siguientes:  
  
-   El complemento se ejecuta en el mismo dominio de aplicación que el host. No le recomendamos esta opción, porque con ella pierde la funcionalidad de aislamiento y descarga que obtiene al utilizar diferentes dominios de aplicación.  
  
-   Varios complementos se cargan en el mismo dominio de aplicación, que es diferente del dominio de aplicación que utiliza el host.  
  
-   Cada complemento se carga exclusivamente en su propio dominio de aplicación. Este nivel de aislamiento es el más común.  
  
-   Varios complementos se cargan en el mismo dominio de aplicación en un proceso externo.  
  
-   Cada complemento se carga exclusivamente en su propio dominio de aplicación en un proceso externo. Este es el escenario más aislado.  
  
 Para obtener más información sobre el uso de procesos externos, consulte [Cómo: activar complementos con diferente seguridad y aislamiento](https://msdn.microsoft.com/library/7afe7ec8-5158-4350-9119-5df0ecab8aa5).  
  
### <a name="lifetime-management"></a>Administración de la duración  
 Dado que el modelo de complementos abarca los límites de proceso y el dominio de aplicación, la recolección de elementos no utilizados, por sí sola, no es suficiente para liberar y recuperar objetos. El modelo de complementos proporciona un mecanismo de administración del ciclo de vida que utiliza recuentos de referencias y tokens y no suele requerir programación adicional. Para obtener más información, consulte [administración de la duración](https://msdn.microsoft.com/library/57a9c87e-394c-4fef-89f2-aa4223a2aeb5).  
  
 [Volver al principio](#top)  
  
<a name="distinguishing_between_addins_and_hosts"></a>   
## <a name="distinguishing-between-add-ins-and-hosts"></a>Distinción entre complementos y hosts  
 La diferencia entre un complemento y un host consiste, simplemente, en que el host es el que activa el complemento. El host puede ser el mayor de los dos, por ejemplo, una aplicación de procesamiento de texto y sus correctores ortográficos. El host también puede ser el menor de los dos, por ejemplo, un cliente de mensajería instantánea con un reproductor multimedia insertado. El modelo de complementos admite complementos en escenarios de cliente y de servidor. Algunos ejemplos de complementos de servidor son los complementos que proporcionan detección de virus, filtros de correo no deseado y protección de IP a los servidores de correo. Ejemplos de complementos de cliente incluyen los complementos de referencia para procesadores de textos, características especializadas para programas de gráficos y juegos y detección de virus para clientes de correo electrónico local.  
  
 [Volver al principio](#top)  
  
<a name="related_topics"></a>   
## <a name="related-topics"></a>Temas relacionados  
  
|Título|Descripción|  
|-----------|-----------------|  
|[Pipeline Development](../../../docs/framework/add-ins/pipeline-development.md)|Describe la canalización de comunicación de los segmentos de la aplicación host al complemento. Proporciona ejemplos de código en los temas de tutoriales que describen cómo construir la canalización y cómo implementar segmentos en la canalización en Visual Studio.|  
|[Dominios de aplicación y ensamblados](https://msdn.microsoft.com/library/433b04ae-4ba8-4849-9dbd-79194f240346)|Describe la relación entre los dominios de aplicación, que proporcionan un límite de aislamiento para la seguridad, la confiabilidad y el control de versiones, además de los ensamblados.|  
  
 [Volver al principio](#top)  
  
<a name="reference"></a>   
## <a name="reference"></a>Referencia  
 <xref:System.AddIn?displayProperty=nameWithType>  
  
 <xref:System.AddIn.Contract?displayProperty=nameWithType>  
  
 <xref:System.AddIn.Hosting?displayProperty=nameWithType>  
  
 <xref:System.AddIn.Pipeline?displayProperty=nameWithType>  
  
 [Volver al principio](#top)