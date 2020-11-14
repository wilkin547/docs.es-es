---
title: Creación y uso de componentes
ms.date: 07/20/2015
helpviewer_keywords:
- components [Visual Basic]
ms.assetid: ee6a4156-73f7-4e9b-8e01-c74c4798b65c
ms.openlocfilehash: 106b8791ee5cb3db95759ccca2fddd799661ef3c
ms.sourcegitcommit: 74d05613d6c57106f83f82ce8ee71176874ea3f0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "93282066"
---
# <a name="creating-and-using-components-in-visual-basic"></a>Crear y utilizar componentes en Visual Basic

Un *componente* es una clase que implementa la interfaz <xref:System.ComponentModel.IComponent?displayProperty=nameWithType> o que deriva directa o indirectamente de una clase que implementa <xref:System.ComponentModel.IComponent>. Un componente de .NET es un objeto que se puede reutilizar, puede interactuar con otros objetos y proporciona control sobre recursos externos y sobre la compatibilidad en tiempo de diseño.  
  
 Una característica importante de los componentes es que se pueden diseñar, lo que significa que se puede usar una clase que es un componente en el entorno de desarrollo integrado de Visual Studio. Los componentes se pueden agregar al cuadro de herramientas, se pueden arrastrar y soltar en un formulario y se pueden manipular en una superficie de diseño. La compatibilidad en tiempo de diseño de los componentes está integrada en .NET. Un desarrollador de componentes no tiene que efectuar ninguna tarea adicional para aprovechar la funcionalidad base del tiempo de diseño.  
  
 Un *control* es similar a un componente, ya que ambos se pueden diseñar, con la diferencia de que un control proporciona una interfaz de usuario, mientras que un componente no. Un control debe derivar de una de las clases de control base: <xref:System.Windows.Forms.Control> o <xref:System.Web.UI.Control>.  
  
## <a name="when-to-create-a-component"></a>Cuándo se debe crear un componente  

 Si la clase se va a usar en una superficie de diseño (como en Windows Forms o en el Diseñador de Web Forms) pero no tiene ninguna interfaz de usuario, debe ser un componente y debe implementar <xref:System.ComponentModel.IComponent>, o bien debe derivarse de una clase que implemente directa o indirectamente <xref:System.ComponentModel.IComponent>.  
  
 Las clases <xref:System.ComponentModel.Component> y <xref:System.ComponentModel.MarshalByValueComponent> son implementaciones base de la interfaz <xref:System.ComponentModel.IComponent>. La principal diferencia entre estas clases es que la clase <xref:System.ComponentModel.Component> se calcula por referencia, mientras que <xref:System.ComponentModel.IComponent> se calcula por valor. En la lista siguiente se proporcionan directrices generales para los implementadores.  
  
- Si el componente se tiene que calcular por referencia, se debe derivar de <xref:System.ComponentModel.Component>.  
  
- Si el componente se tiene que calcular por valor, se debe derivar de <xref:System.ComponentModel.MarshalByValueComponent>.  
  
- Si el componente no se puede derivar de una de las implementaciones base debido a la herencia única, implemente <xref:System.ComponentModel.IComponent>.  
  
## <a name="component-classes"></a>Clases de componentes  

 El espacio de nombres <xref:System.ComponentModel> proporciona clases que se usan para implementar el comportamiento de los componentes y controles en tiempo de diseño y en tiempo de ejecución. Este espacio de nombres incluye las clases bases y las interfaces para implementar atributos y convertidores de tipos, enlazarlos con orígenes de datos y generar licencias para los componentes.  
  
 Las clases de componentes básicas son las siguientes:  
  
- <xref:System.ComponentModel.Component>. Una implementación base para la interfaz <xref:System.ComponentModel.IComponent>. Esta clase permite el uso compartido de objetos entre aplicaciones.  
  
- <xref:System.ComponentModel.MarshalByValueComponent>. Una implementación base para la interfaz <xref:System.ComponentModel.IComponent>.  
  
- <xref:System.ComponentModel.Container>. La implementación base de la interfaz <xref:System.ComponentModel.IContainer>. Esta clase encapsula cero o más componentes.  
  
 Algunas de las clases usadas para la generación de licencias de componentes son las siguientes:  
  
- <xref:System.ComponentModel.License>. Clase base abstracta para todas las licencias. Las licencias se conceden a una instancia específica de un componente.  
  
- <xref:System.ComponentModel.LicenseManager>. Proporciona propiedades y métodos para agregar una licencia a un componente y administrar un <xref:System.ComponentModel.LicenseProvider>.  
  
- <xref:System.ComponentModel.LicenseProvider>. Clase base abstracta para implementar un proveedor de licencias.  
  
- <xref:System.ComponentModel.LicenseProviderAttribute>. Especifica la clase <xref:System.ComponentModel.LicenseProvider> que se va a usar con una clase.  
  
 Clases usadas habitualmente para describir y conservar componentes.  
  
- <xref:System.ComponentModel.TypeDescriptor>. Proporciona información sobre las características de un componente, como sus atributos, propiedades y eventos.  
  
- <xref:System.ComponentModel.EventDescriptor>. Proporciona información sobre un evento.  
  
- <xref:System.ComponentModel.PropertyDescriptor>. Proporciona información sobre una propiedad.  
  
## <a name="related-sections"></a>Secciones relacionadas  

 [Solución de problemas relacionados con la creación de controles y componentes](/dotnet/desktop/winforms/controls/troubleshooting-control-and-component-authoring)  
 Se explica cómo solucionar problemas comunes.  
  
## <a name="see-also"></a>Vea también

- [Cómo: Obtener acceso a las funciones en tiempo de diseño de formularios Windows Forms](/dotnet/desktop/winforms/controls/developing-windows-forms-controls-at-design-time)
