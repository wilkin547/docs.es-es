---
title: Desarrollo de canalizaciones
ms.date: 03/30/2017
helpviewer_keywords:
- add-in pipeline [.NET Framework], segments
- activation path for add-ins [.NET Framework]
- add-in pipeline [.NET Framework], activation path
- communication pipeline for add-ins [.NET Framework]
- add-in pipeline [.NET Framework], about
- add-ins [.NET Framework], pipeline development
ms.assetid: 932788f2-b87d-44cf-82f9-04492a8b2722
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 047cd7a2b8a6d315c6cadb9b535b84f744fd2d09
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43504890"
---
# <a name="pipeline-development"></a>Desarrollo de canalizaciones
La canalización de complementos es la ruta de acceso de los segmentos de canalización que la aplicación host y su complemento, deben usar para comunicarse entre sí.  
  
 La siguiente ilustración muestra la canalización de comunicación y de sus segmentos.  
  
 ![Agregar&#45;en el modelo de canalización. ](../../../docs/framework/add-ins/media/addin1.png "AddIn1")  
Canalización de complementos  
  
 La aplicación host es de un extremo de la canalización y el complemento se encuentra en el otro extremo. A partir de cada extremo y desplazándose hacia el centro, la aplicación host y el complemento tienen una clase base abstracta que define una vista del modelo de objetos que ambos comparten. Estos tipos (clases) conforman el segmento de canalización de la vista de complemento y la vista de host del segmento de canalización de complementos. El segmento de canalización de la vista de complemento a menudo contiene más de una clase abstracta, pero la clase que el complemento hereda se conoce como la base de complemento.  
  
 El segmento de canalización del adaptador de conversión de agregar y el convertir de segmento de canalización el flujo de tipos entre los segmentos de canalización de la vista y el segmento de canalización del contrato de adaptador del host. El segmento central de la canalización es un contrato que se deriva el <xref:System.AddIn.Contract.IContract> interfaz. Este contrato define los métodos que la aplicación host y su complemento a utilizar.  
  
 Si el host y el complemento se carga en dominios de aplicación independiente, tiene un límite de aislamiento que separa el ámbito de la aplicación host desde el ámbito del complemento. El contrato es el único ensamblado se carga en el host y los dominios de aplicación del complemento. El host y el complemento con cada referencia únicamente a su vista de los métodos del contrato. Por lo tanto, se separan mediante una capa de abstracción del contrato.  
  
 Para desarrollar segmentos de canalización, debe crear una estructura de directorios que se va a contener. Para obtener más información sobre los requisitos de desarrollo e instrucciones de ámbito, consulte [Pipeline Development Requirements](https://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5).  
  
 La siguiente ilustración muestra los tipos que conforman los segmentos de canalización. Los nombres de los tipos que aparecen en la ilustración son arbitrarios, pero ver todos los tipos excepto el host y el host de los atributos del complemento necesitan por lo que se pueden detectar mediante métodos que construcción un almacén de información.  
  
 ![Agregar&#45;en el modelo con atributos requeridos en tipos. ](../../../docs/framework/add-ins/media/addin-model.png "AddIn_Model")  
Canalización de complementos con tipos  
  
 En la tabla siguiente se describe los segmentos de canalización para activar un complemento. Para obtener más información acerca de estos segmentos, consulte [contratos, vistas y adaptadores](https://msdn.microsoft.com/library/a6460173-9507-4b87-8c07-d4ee245d715c).  
  
|Segmento de canalización|Descripción|  
|----------------------|-----------------|  
|administrador de flujos de trabajo|El ensamblado de aplicación que crea una instancia de un complemento.|  
|Vista de host del complemento:|Representa la vista de la aplicación host de los tipos de objeto y los métodos utilizados para comunicarse con el complemento. La vista del host es una interfaz o clase base abstracta.|  
|Adaptador del host|Un ensamblado con una o más clases que se adapta a los métodos para y desde el contrato.<br /><br /> Este segmento de canalización se identifica mediante el <xref:System.AddIn.Pipeline.HostAdapterAttribute> atributo.<br /><br /> No se admiten ensamblados de varios módulos.|  
|Contrato|Una interfaz que se deriva el <xref:System.AddIn.Contract.IContract> interfaz y que define el protocolo para la comunicación de tipos entre el host y su complemento.<br /><br /> Este segmento de canalización se identifica estableciendo la <xref:System.AddIn.Pipeline.AddInContractAttribute> atributo.|  
|Adaptador de conversión|Un ensamblado con una o más clases que se adapta a los métodos para y desde el contrato.<br /><br /> Este segmento de canalización se identifica mediante el <xref:System.AddIn.Pipeline.AddInAdapterAttribute> atributo.<br /><br /> Cada ensamblado en el directorio de adaptador de complemento en el lado que contiene un tipo que tiene un <xref:System.AddIn.Pipeline.AddInAdapterAttribute> atributo se carga en dominio de aplicación del complemento.<br /><br /> Cada ensamblado en el directorio de agregar en el lado se carga en su propio dominio de aplicación.<br /><br /> No se admiten ensamblados de varios módulos|  
|Vista de complemento|Un ensamblado que representa la vista del complemento de los tipos de objetos y métodos que se usan para comunicarse con el host. La vista de complemento es una interfaz o clase base abstracta.<br /><br /> Este segmento de canalización se identifica mediante el <xref:System.AddIn.Pipeline.AddInBaseAttribute> atributo.<br /><br /> Cada ensamblado en el directorio AddInViews que contiene un tipo que tiene un <xref:System.AddIn.Pipeline.AddInBaseAttribute> atributo se carga en dominio de aplicación del complemento.|  
|Complemento|Un tipo con instancias que realiza un servicio para el host.|  
  
## <a name="pipeline-activation-path"></a>Ruta de activación de canalización  
 La siguiente ilustración muestra la activación de tipos cuando se activa un complemento. También se muestra la transferencia de objetos para el host, como los resultados de un cálculo o una colección de objetos. Este es el escenario más típico.  
  
 ![Agregar&#45;en el modelo con la ruta de activación. ](../../../docs/framework/add-ins/media/addin6.png "AddIn6")  
Ruta de activación desde el complemento al host  
  
 La ruta de acceso de activación de la canalización se produce como sigue:  
  
1.  La aplicación host activa el complemento con el <xref:System.AddIn.Hosting.AddInToken.Activate%2A> método.  
  
2.  Los ensamblados de contrato, el adaptador del complemento y la vista de complemento, complementos se cargan en dominio de aplicación del complemento.  
  
3.  Se crea una instancia de que el adaptador de conversión mediante la vista de complemento (con la clase identificada por el <xref:System.AddIn.Pipeline.AddInBaseAttribute> atributo) como su constructor. El adaptador de conversión hereda del contrato.  
  
4.  El adaptador de complemento en el lado que se escribe como el contrato, se pasa a través del límite de aislamiento (opcional) al constructor del adaptador del host.  
  
5.  La vista del host del adaptador de complemento, el lado del host y los ensamblados de contrato se cargan en el dominio de aplicación del host.  
  
6.  Se crea una instancia del adaptador del host utilizando el contrato como su constructor. El adaptador del host hereda de la vista host del complemento.  
  
7.  El host tiene el complemento, que se escribe como el host de vista de complemento y puede seguir llamando a sus métodos.  
  
## <a name="walkthroughs"></a>Tutoriales  
 Hay tres temas de tutoriales que describen cómo crear canalizaciones mediante Visual Studio:  
  
-   [Tutorial: Creación de una aplicación extensible](../../../docs/framework/add-ins/walkthrough-create-extensible-app.md)  
  
     Describe un complemento de calculadora que realiza la suma, resta, multiplicación y división cálculos para el host.  
  
-   [Tutorial: Habilitar la compatibilidad con versiones anteriores como los cambios de Host](https://msdn.microsoft.com/library/6fa15bb5-8f04-407d-bd7d-675dc043c848)  
  
     Describe un complemento de calculadora con capacidades de cálculo mejoradas y cómo mantener la compatibilidad con el primer complemento de calculadora.  
  
-   [Tutorial: Pasar colecciones entre Hosts y complementos](https://msdn.microsoft.com/library/b532c604-548e-4fab-b11c-377257dd0ee5)  
  
     Describe cómo pasar colecciones de datos a través de la canalización con un escenario de almacén de libro.  
  
## <a name="see-also"></a>Vea también  
 [Escenarios de canalización del complemento](https://msdn.microsoft.com/library/feb70e0b-8734-494c-aeaf-b567f014043e)  
 [Complementos y extensibilidad](../../../docs/framework/add-ins/index.md)
