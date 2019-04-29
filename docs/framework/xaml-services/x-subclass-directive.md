---
title: x:Subclass (Directiva)
ms.date: 03/30/2017
f1_keywords:
- Subclass
- xSubclass
- x:Subclass
helpviewer_keywords:
- x:Subclass attribute [XAML Services]
- XAML [XAML Services], x:Subclass attribute
- Subclass attribute in XAML [XAML Services]
ms.assetid: 99f66072-8107-4362-ab99-8171dc83b469
ms.openlocfilehash: 850fe8acf9e47149bd385e78b30e04ba77d7a8b2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61938871"
---
# <a name="xsubclass-directive"></a>x:Subclass (Directiva)
Modifica el comportamiento de compilación de marcado XAML cuando `x:Class` también se proporciona. En lugar de crear una clase parcial que se basa en `x:Class`, proporcionado `x:Class` se crea como una clase intermedia, y, a continuación, se espera que la clase derivada proporcionada basarse en `x:Class`.  
  
## <a name="xaml-attribute-usage"></a>Uso de atributos XAML  
  
```  
<object x:Class="namespace.classname" x:Subclass="subclassNamespace.subclassName">  
   ...  
</object>  
```  
  
## <a name="xaml-values"></a>Valores XAML  
  
|||  
|-|-|  
|`namespace`|Opcional. Especifica un espacio de nombres CLR que contiene `classname`. Si `namespace` se especifica un punto (.) separa `namespace` y `classname`.|  
|`classname`|Obligatorio. Especifica el nombre CLR de la clase parcial que conecta el XAML cargado y el código subyacente para esa XAML. Vea la sección Comentarios.|  
|`subclassNamespace`|Opcional. Puede ser diferente de `namespace` si cada espacio de nombres puede resolver el otro. Especifica un espacio de nombres CLR que contiene `subclassName`. Si `subclassName` se especifica un punto (.) separa `subclassNamespace` y `subclassName`.|  
|`subclassName`|Obligatorio. Especifica el nombre de la subclase CLR.|  
  
## <a name="dependencies"></a>Dependencias  
 [x: Class directiva](x-class-directive.md) también debe proporcionarse en el mismo objeto, y ese objeto debe ser el elemento raíz de la producción de XAML.  
  
## <a name="remarks"></a>Comentarios  
 `x:Subclass` uso sirve principalmente para los idiomas que no admiten las declaraciones de clase parcial.  
  
 La clase se utiliza como el `x:Subclass` no puede ser una clase anidada, y `x:Subclass` debe hacer referencia al objeto raíz como se explica en la sección "Dependencias".  
  
 En caso contrario, el significado conceptual de `x:Subclass` no está definida por una implementación de servicios XAML de .NET Framework. Esto es porque el comportamiento de los servicios XAML de .NET Framework no especifica el modelo de programación general por qué XAML marcado y código de respaldo están conectados. Relacionados con las implementaciones de conceptos más extensos `x:Class` y `x:Subclass` se realizan mediante marcos concretos que usan modelos de programación o modelos de aplicación para definir cómo conectar el marcado XAML compilado marcado y código subyacente basado en CLR. Cada marco de trabajo podría tener sus propias acciones de compilación que habilitan algunos de los componentes específicos que deben incluirse en el entorno de compilación o comportamiento. Dentro de un marco, las acciones de compilación también pueden variar según el lenguaje específico de CLR que se usa para el código subyacente.  
  
## <a name="wpf-usage-notes"></a>Notas de uso WPF  
 `x:Subclass` puede estar en una raíz de la página o en el <xref:System.Windows.Application> raíz en la definición de aplicación, que ya tiene `x:Class`. Declarar `x:Subclass` en cualquier elemento que no sea una raíz de la página o aplicación, o de especificarla donde no `x:Class` existe, se produce un error de tiempo de compilación.  
  
 Crear derivada de las clases que funcionan correctamente para el `x:Subclass` escenario es bastante complejo. Es posible que deba examinar los archivos intermedios (los archivos. g generados en la carpeta obj del proyecto mediante la compilación de marcado, con nombres que incorporan los nombres de archivo .xaml). Estos archivos intermedios pueden ayudarle a determinar el origen de determinadas construcciones de programación en las clases parciales combinadas en la aplicación compilada.  
  
 Controladores de eventos en la clase derivada deben ser `internal override` (`Friend Overrides` en Microsoft Visual Basic) con el fin de invalidar los códigos auxiliares para los controladores, tal y como se crea en la clase intermedia durante la compilación. En caso contrario, las implementaciones de la clase derivada ocultar la implementación de clase intermedia (instantáneas) y no se invocan los controladores de clase intermedia.  
  
 Al definir ambos `x:Class` y `x:Subclass`, no es necesario proporcionar ninguna implementación de la clase que hace referencia `x:Class`. Solo deberá asignarle un nombre a través de la `x:Class` atributo para que el compilador tiene algunas instrucciones para la clase que crea en los archivos intermedios (el compilador no selecciona un nombre predeterminado en este caso). Puedes usar el `x:Class` una implementación de la clase; sin embargo, esto no es el escenario típico para usar ambos `x:Class` y `x:Subclass`.  
  
## <a name="see-also"></a>Vea también

- [x:Class (Directiva)](x-class-directive.md)
- [Clases XAML y personalizadas para WPF](../wpf/advanced/xaml-and-custom-classes-for-wpf.md)
