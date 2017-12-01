---
title: Crear y utilizar componentes en Visual Basic
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords: components [Visual Basic]
ms.assetid: ee6a4156-73f7-4e9b-8e01-c74c4798b65c
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 453d341961207dd851136aa47a52759b0841424d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="creating-and-using-components-in-visual-basic"></a>Crear y utilizar componentes en Visual Basic
Un *componente* es una clase que implementa la interfaz <xref:System.ComponentModel.IComponent?displayProperty=nameWithType> o que deriva directa o indirectamente de una clase que implementa <xref:System.ComponentModel.IComponent>. Un componente de [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] es un objeto que se puede reutilizar, puede interactuar con otros objetos y proporciona control sobre recursos externos y sobre la compatibilidad en tiempo de diseño.  
  
 Una característica importante de los componentes es que se pueden diseñar, lo que significa que se puede usar una clase que es un componente en el entorno de desarrollo integrado de [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]. Los componentes se pueden agregar al cuadro de herramientas, se pueden arrastrar y soltar en un formulario y se pueden manipular en una superficie de diseño. Observe que la compatibilidad en tiempo de diseño de los componentes está integrada en [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]; un programador de componentes no tiene que efectuar ninguna tarea adicional para aprovechar las funcionalidades base del tiempo de diseño.  
  
 Un *control* es similar a un componente, ya que ambos se pueden diseñar, con la diferencia de que un control proporciona una interfaz de usuario, mientras que un componente no. Un control debe derivar de una de las clases de control base: <xref:System.Windows.Forms.Control> o <xref:System.Web.UI.Control>.  
  
## <a name="when-to-create-a-component"></a>Cuándo se debe crear un componente  
 Si la clase se va a usar en una superficie de diseño (como en Windows Forms o en el Diseñador de Web Forms) pero no tiene ninguna interfaz de usuario, debe ser un componente y debe implementar <xref:System.ComponentModel.IComponent>, o bien debe derivarse de una clase que implemente directa o indirectamente <xref:System.ComponentModel.IComponent>.  
  
 Las clases <xref:System.ComponentModel.Component> y <xref:System.ComponentModel.MarshalByValueComponent> son implementaciones base de la interfaz <xref:System.ComponentModel.IComponent>. La principal diferencia entre estas clases es que la clase <xref:System.ComponentModel.Component> se calcula por referencia, mientras que <xref:System.ComponentModel.IComponent> se calcula por valor. En la lista siguiente se proporcionan directrices generales para los implementadores.  
  
-   Si el componente se tiene que calcular por referencia, se debe derivar de <xref:System.ComponentModel.Component>.  
  
-   Si el componente se tiene que calcular por valor, se debe derivar de <xref:System.ComponentModel.MarshalByValueComponent>.  
  
-   Si el componente no se puede derivar de una de las implementaciones base debido a la herencia única, implemente <xref:System.ComponentModel.IComponent>.  
  
 Para obtener más información sobre la compatibilidad en tiempo de diseño, vea [Atributos en tiempo de diseño para componentes](http://msdn.microsoft.com/library/12050fe3-9327-4509-9e21-4ee2494b95c3) y [Ampliar compatibilidad en tiempo de diseño](http://msdn.microsoft.com/library/d6ac8a6a-42fd-4bc8-bf33-b212811297e2).  
  
## <a name="component-classes"></a>Clases de componentes  
 El espacio de nombres <xref:System.ComponentModel> proporciona clases que se usan para implementar el comportamiento de los componentes y controles en tiempo de diseño y en tiempo de ejecución. Este espacio de nombres incluye las clases bases y las interfaces para implementar atributos y convertidores de tipos, enlazarlos con orígenes de datos y generar licencias para los componentes.  
  
 Las clases de componentes básicas son las siguientes:  
  
-   <xref:System.ComponentModel.Component>. Una implementación base para la interfaz <xref:System.ComponentModel.IComponent>. Esta clase permite el uso compartido de objetos entre aplicaciones.  
  
-   <xref:System.ComponentModel.MarshalByValueComponent>. Una implementación base para la interfaz <xref:System.ComponentModel.IComponent>.  
  
-   <xref:System.ComponentModel.Container>. La implementación base de la interfaz <xref:System.ComponentModel.IContainer>. Esta clase encapsula cero o más componentes.  
  
 Algunas de las clases usadas para la generación de licencias de componentes son las siguientes:  
  
-   <xref:System.ComponentModel.License>. Clase base abstracta para todas las licencias. Las licencias se conceden a una instancia específica de un componente.  
  
-   <xref:System.ComponentModel.LicenseManager>. Proporciona propiedades y métodos para agregar una licencia a un componente y administrar un <xref:System.ComponentModel.LicenseProvider>.  
  
-   <xref:System.ComponentModel.LicenseProvider>. Clase base abstracta para implementar un proveedor de licencias.  
  
-   <xref:System.ComponentModel.LicenseProviderAttribute>. Especifica la clase <xref:System.ComponentModel.LicenseProvider> que se va a usar con una clase.  
  
 Clases usadas habitualmente para describir y conservar componentes.  
  
-   <xref:System.ComponentModel.TypeDescriptor>. Proporciona información sobre las características de un componente, como sus atributos, propiedades y eventos.  
  
-   <xref:System.ComponentModel.EventDescriptor>. Proporciona información sobre un evento.  
  
-   <xref:System.ComponentModel.PropertyDescriptor>. Proporciona información sobre una propiedad.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Clase frente a componente y frente a control](http://msdn.microsoft.com/library/db8b842e-44d9-40cc-a0f8-70fd189632c3)  
 Define *componente* y *control* y describe las diferencias existentes entre estos y las clases.  
  
 [Creación de componentes](http://msdn.microsoft.com/library/4a5a5e49-0378-4a31-83bc-24da0f1a727d)  
 Guía de introducción a los componentes.  
  
 [Tutoriales sobre la creación de componentes](http://msdn.microsoft.com/library/c414cca9-2489-4208-8b38-954586d91c13)  
 Vínculos a temas que proporcionan instrucciones paso a paso para la programación de componentes.  
  
 [Clases de componentes](http://msdn.microsoft.com/library/ce2e5647-e673-4c2b-8125-ffebbd9d71bc)  
 Se describe lo que convierte una clase en un componente, maneras de exponer la funcionalidad de los componentes, controlar el acceso a componentes y controlar cómo se crean instancias de los componentes.  
  
 [Solución de problemas relacionados con la creación de controles y componentes](../../framework/winforms/controls/troubleshooting-control-and-component-authoring.md)  
 Se explica cómo solucionar problemas comunes.  
  
## <a name="see-also"></a>Vea también  
 [Cómo: obtener acceso a la compatibilidad en tiempo de diseño en formularios Windows Forms](http://msdn.microsoft.com/library/a84f8579-1f47-41b9-ba37-69030b0aff09)  
 [Cómo: Extender la apariencia y el comportamiento de los controles en modo de diseño](http://msdn.microsoft.com/library/68f85054-2253-47f5-a4f2-3f1ac8c9f27b)  
 [Cómo: Llevar a cabo una inicialización personalizada de controles en modo de diseño](http://msdn.microsoft.com/library/914eaa03-092f-4556-9160-b8a2a40641d9)
