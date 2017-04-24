---
title: "Propiedades de dependencia de s&#243;lo lectura | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "propiedades de dependencia, solo lectura"
  - "propiedades de dependencia de sólo lectura"
ms.assetid: f23d6ec9-3780-4c09-a2ff-b2f0a2deddf1
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Propiedades de dependencia de s&#243;lo lectura
En este tema se describen las propiedades de dependencia de sólo lectura; se incluyen las ya existentes, así como los escenarios y las técnicas para crear una personalizada.  
  
   
  
<a name="prerequisites"></a>   
## Requisitos previos  
 En este tema se supone que entiende los escenarios básicos de la implementación de una propiedad de dependencia, así como la aplicación de una propiedad a una propiedad de dependencia personalizada.  Vea [Propiedades de dependencia personalizadas](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md) y [Metadatos de las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md) para obtener contexto.  
  
<a name="existing"></a>   
## Propiedades de la dependencia de sólo lectura existentes  
 Algunas de las propiedades de dependencia definidos en el marco de trabajo de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] son de sólo lectura.  El motivo habitual típica para especificar una propiedad de dependencia de sólo lectura es que se trata de propiedades deben utilizarse para determinar el estado en casos en que hay muchos factores que afectan a este último, pero en los que limitarse a establecer la propiedad en ese estado no es deseable desde el punto de vista del diseño de la interfaz de usuario.  Por ejemplo, la propiedad <xref:System.Windows.UIElement.IsMouseOver%2A> se limita, en realidad, a exponer el estado determinado por la entrada de mouse.  Cualquier intento de establecer este valor mediante programación y eludir la entrada de mouse real sería imprevisible y daría lugar a incoherencias.  
  
 Al no poder establecerse, las propiedades de dependencia de sólo lectura no son adecuadas para muchos de los escenarios en que las propiedades de dependencia suelen ofrecer una solución \(a saber: enlace de datos, aplicación de un estilo directo a un valor, validación, animación o herencia\).  A pesar de no poderse establecer, las propiedades de dependencia de sólo lectura conservan algunas de las funciones adicionales que admiten las propiedades de dependencia en el sistema de propiedades.  De éstas, la más importante es la capacidad de ser utilizadas como desencadenador de propiedad en un estilo.  Los desencadenadores no se pueden habilitar con una propiedad [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] normal; se necesita una propiedad de dependencia.  La propiedad <xref:System.Windows.UIElement.IsMouseOver%2A> mencionada anteriormente es un ejemplo perfecto de un escenario donde podría resultar de gran utilidad definir un estilo para un control, donde alguna propiedad visible, como el fondo, el primer plano u otras propiedades similares de elementos compuestos dentro del control cambiará cuando el usuario sitúe un mouse sobre alguna zona definida del control.  Los procesos de invalidación inherentes al sistema de propiedades pueden detectar y comunicar los cambios de una propiedad de dependencia de sólo lectura, lo que constituye la compatibilidad interna con la funcionalidad de desencadenador de propiedad.  
  
<a name="new"></a>   
## Crear propiedades de dependencia de sólo lectura personalizadas  
 Asegúrese de leer la sección anterior sobre los motivos por los que las propiedades de dependencia de sólo lectura no funcionan en muchos escenarios de propiedades de dependencia típicos.  Sin embargo, si el escenario es el adecuado, puede ser conveniente crear su propia propiedad de dependencia de sólo lectura.  
  
 Gran parte del proceso de creación de una propiedad de dependencia de sólo lectura es igual al descrito en los temas [Propiedades de dependencia personalizadas](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md) y [Implementar una propiedad de dependencia](../../../../docs/framework/wpf/advanced/how-to-implement-a-dependency-property.md).  Hay tres diferencias importantes:  
  
-   Al registrar la propiedad, llame al método <xref:System.Windows.DependencyProperty.RegisterReadOnly%2A> en lugar de al método <xref:System.Windows.DependencyProperty.Register%2A> normal para el registro de propiedades.  
  
-   Al implementar la propiedad de "contenedor" de [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)], asegúrese de que tampoco el contenedor tenga una implementación de establecimiento, de tal forma que no haya ninguna incoherencia en el estado de sólo lectura para el contenedor público que se expone.  
  
-   El objeto devuelto por el registro de sólo lectura es <xref:System.Windows.DependencyPropertyKey> en lugar de <xref:System.Windows.DependencyProperty>.  Este campo debe almacenarse igualmente como miembro, pero no es habitual convertirlo en un miembro público del tipo.  
  
 Por supuesto, el valor o campo privado que respalda la propiedad de dependencia de sólo lectura puede ser de lectura y escritura con la lógica que usted decida.  Sin embargo, la manera más sencilla de establecer la propiedad, ya sea inicialmente o como parte de lógica de tiempo de ejecución, es utilizar las [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] del sistema de propiedades, en lugar de eludir el sistema de propiedades y establecer directamente el campo de respaldo privado.  En particular, existe una firma de <xref:System.Windows.DependencyObject.SetValue%2A> que acepta un parámetro de tipo <xref:System.Windows.DependencyPropertyKey>.  Cómo y dónde se establezca este valor mediante programación dentro de la lógica de la aplicación afectará a cómo se establecerá el acceso en la <xref:System.Windows.DependencyPropertyKey> creada al registrar la propiedad de dependencia por primera vez.  Si toda esta lógica se administra dentro de la clase, puede hacerlo privado, pero si requiere que se establezca desde otro componente del ensamblado, puede establecerlo como interno.  Un enfoque consiste en llamar a <xref:System.Windows.DependencyObject.SetValue%2A> dentro de un controlador de eventos de clase de un evento pertinente que comunique a una instancia de clase que es preciso cambiar el valor de propiedad almacenado.  Otro enfoque consiste en vincular las propiedades de dependencia entre sí mediante devoluciones de llamada <xref:System.Windows.PropertyChangedCallback> y <xref:System.Windows.CoerceValueCallback> emparejadas como parte de los metadatos de esas propiedades durante el registro.  
  
 Dado que <xref:System.Windows.DependencyPropertyKey> es privada, y que el sistema de propiedades no la propaga fuera del código, una propiedad de dependencia de sólo lectura aporta mayor seguridad de establecimiento que una propiedad de dependencia de lectura y escritura.  Para una propiedad de dependencia de lectura y escritura, el campo de identificación es público de manera explícita o implícita, con lo que la propiedad se puede establecer ampliamente.  Para obtener información más específica, vea [Seguridad de las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-property-security.md).  
  
## Vea también  
 [Información general sobre las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)   
 [Propiedades de dependencia personalizadas](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)   
 [Aplicar estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md)