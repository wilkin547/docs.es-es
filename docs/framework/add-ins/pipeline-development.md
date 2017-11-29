---
title: Desarrollo de canalizaciones
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- add-in pipeline [.NET Framework], segments
- activation path for add-ins [.NET Framework]
- add-in pipeline [.NET Framework], activation path
- communication pipeline for add-ins [.NET Framework]
- add-in pipeline [.NET Framework], about
- add-ins [.NET Framework], pipeline development
ms.assetid: 932788f2-b87d-44cf-82f9-04492a8b2722
caps.latest.revision: "31"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4991fc65a48d620d30d09c44f1a30c2d1839071e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="pipeline-development"></a>Desarrollo de canalizaciones
La canalización de complementos es la ruta de acceso de los segmentos de canalización que la aplicación host y su complemento deben utilizar para comunicarse entre sí.  
  
 En la siguiente ilustración se muestra la canalización de comunicación y sus segmentos.  
  
 ![Agregar &#45; en el modelo de canalización. ] (../../../docs/framework/add-ins/media/addin1.png "AddIn1")  
Canalización de complementos  
  
 La aplicación host se encuentra en un extremo de la canalización y el complemento está en el otro extremo. Comenzando desde cada extremo y desplazándose hacia el centro, la aplicación host y el complemento tienen una clase base abstracta que define una vista del modelo de objetos que ambos comparten. Estos tipos (clases) constituyen el segmento de canalización de la vista de complemento y la vista de host del segmento de canalización de complementos. El segmento de canalización del complemento de vista a menudo contiene más de una clase abstracta, pero la clase que hereda de se conoce como la base de complemento.  
  
 El segmento de canalización del adaptador de complemento de conversión y la conversión de segmento de canalización de adaptador de host el flujo de tipos entre los segmentos de canalización de la vista y el segmento de canalización del contrato. El segmento central de la canalización es un contrato que se deriva de la <xref:System.AddIn.Contract.IContract> interfaz. Este contrato define los métodos que la aplicación host y su complemento a utilizar.  
  
 Si carga el host y el complemento en dominios de aplicación independientes, tiene un límite de aislamiento que separa el ámbito de la aplicación host del ámbito del complemento. El contrato es el único ensamblado que se carga en el host y los dominios de aplicación del complemento. El host y el complemento de cada solo hacer referencia a la vista de los métodos de contrato. Por lo tanto, se separan mediante una capa de abstracción del contrato.  
  
 Para desarrollar segmentos de canalización, debe crear una estructura de directorios que se va a contener. Para obtener más información sobre los requisitos de desarrollo y directrices de ámbito, consulte [requisitos del desarrollo de canalizaciones](http://msdn.microsoft.com/en-us/ef9fa986-e80b-43e1-868b-247f4c1d9da5).  
  
 En la siguiente ilustración se muestra los tipos que conforman los segmentos de canalización. Los nombres de los tipos que se muestra en la ilustración son arbitrarios, pero todos los tipos excepto el host y el host de vista de los atributos de complemento requieren para que puedan ser detectados por los métodos que crear un almacén de información.  
  
 ![Agregar &#45; en el modelo con atributos requeridos en tipos. ] (../../../docs/framework/add-ins/media/addin-model.png "AddIn_Model")  
Canalización de complementos con tipos  
  
 La tabla siguiente describen los segmentos de canalización para activar un complemento. Para obtener más información acerca de estos segmentos, vea [contratos, vistas y adaptadores](http://msdn.microsoft.com/en-us/a6460173-9507-4b87-8c07-d4ee245d715c).  
  
|Segmento de la canalización|Descripción|  
|----------------------|-----------------|  
|Host|El ensamblado de aplicación que crea una instancia de un complemento.|  
|Vista de host del complemento|Representa la vista de la aplicación host de los tipos de objeto y los métodos que se utilizan para comunicarse con el complemento. La vista de host es una interfaz o clase base abstracta.|  
|Adaptador de host|Un ensamblado con una o más clases que adapta los métodos al contrato y viceversa.<br /><br /> Este segmento de la canalización se identifica mediante el <xref:System.AddIn.Pipeline.HostAdapterAttribute> atributo.<br /><br /> No se admiten ensamblados de varios módulos.|  
|Contrato|Una interfaz que se deriva de la <xref:System.AddIn.Contract.IContract> interfaz que define el protocolo para la comunicación entre el host y su complemento.<br /><br /> Este segmento de la canalización se identifica estableciendo la <xref:System.AddIn.Pipeline.AddInContractAttribute> atributo.|  
|Adaptador de conversión|Un ensamblado con una o más clases que adapta los métodos al contrato y viceversa.<br /><br /> Este segmento de la canalización se identifica mediante el <xref:System.AddIn.Pipeline.AddInAdapterAttribute> atributo.<br /><br /> Cada ensamblado en el directorio de adaptador de complemento en el lado que contiene un tipo que tiene un <xref:System.AddIn.Pipeline.AddInAdapterAttribute> atributo se carga en dominio de aplicación del complemento.<br /><br /> Cada ensamblado en el directorio de lado de complemento se carga en su propio dominio de aplicación.<br /><br /> No se admiten ensamblados de varios módulos|  
|Vista de complemento|Un ensamblado que representa la vista del complemento de los tipos de objetos y métodos que se usan para comunicarse con el host. La vista del complemento es una interfaz o clase base abstracta.<br /><br /> Este segmento de la canalización se identifica mediante el <xref:System.AddIn.Pipeline.AddInBaseAttribute> atributo.<br /><br /> Cada ensamblado en el directorio AddInViews que contiene un tipo que tiene un <xref:System.AddIn.Pipeline.AddInBaseAttribute> atributo se carga en dominio de aplicación del complemento.|  
|Complemento|Un tipo con instancias que realiza un servicio para el host.|  
  
## <a name="pipeline-activation-path"></a>Ruta de activación de canalización  
 En la siguiente ilustración muestra la activación de tipos cuando se activa un complemento. También se muestra la transferencia de objetos para el host, como los resultados de un cálculo o una colección de objetos. Este es el escenario más típico.  
  
 ![Agregar &#45; en el modelo con ruta de activación. ] (../../../docs/framework/add-ins/media/addin6.png "AddIn6")  
Ruta de acceso de activación desde el complemento al host  
  
 La ruta de acceso de activación de la canalización se produce como sigue:  
  
1.  La aplicación host activa el complemento con el <xref:System.AddIn.Hosting.AddInToken.Activate%2A> método.  
  
2.  La vista del complemento, complemento, adaptador de complemento de conversión y los ensamblados de contrato se cargan en dominio de aplicación del complemento.  
  
3.  Se crea una instancia del adaptador de complemento de conversión mediante la vista de complemento (con la clase identificada por la <xref:System.AddIn.Pipeline.AddInBaseAttribute> atributo) como su constructor. El adaptador de conversión hereda del contrato.  
  
4.  El adaptador de complemento de conversión, que se escribe como el contrato, se pasa a través del límite de aislamiento (opcional) al constructor del adaptador del host.  
  
5.  La vista de host del adaptador de complemento, del host y los ensamblados de contrato se cargan en el dominio de aplicación del host.  
  
6.  Se crea una instancia del adaptador del host utilizando el contrato como su constructor. El adaptador del host hereda de la vista de host del complemento.  
  
7.  El host tiene el complemento, que se escribe ver del complemento, el host, y puede seguir llamando a sus métodos.  
  
## <a name="walkthroughs"></a>Tutoriales  
 Hay tres temas del tutorial que describen cómo crear canalizaciones mediante Visual Studio:  
  
-   [Tutorial: Crear una aplicación Extensible](../../../docs/framework/add-ins/walkthrough-create-extensible-app.md)  
  
     Describe un complemento de calculadora que realiza la suma, resta, multiplicación y división cálculos para el host.  
  
-   [Tutorial: Habilitar la compatibilidad con versiones anteriores como los cambios de Host](http://msdn.microsoft.com/en-us/6fa15bb5-8f04-407d-bd7d-675dc043c848)  
  
     Describe un complemento de calculadora con capacidades de cálculo mejoradas y cómo mantener la compatibilidad con el primer complemento de calculadora.  
  
-   [Tutorial: Pasar colecciones entre Hosts y complementos](http://msdn.microsoft.com/en-us/b532c604-548e-4fab-b11c-377257dd0ee5)  
  
     Describe cómo pasar colecciones de datos a través de la canalización utilizando un escenario de almacén de libros.  
  
## <a name="see-also"></a>Vea también  
 [Escenarios de canalización del complemento](http://msdn.microsoft.com/en-us/feb70e0b-8734-494c-aeaf-b567f014043e)  
 [Complementos y extensibilidad](../../../docs/framework/add-ins/index.md)
