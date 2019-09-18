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
ms.openlocfilehash: f6f02998a7648693bd731d6b2afdfd4499abaa04
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053909"
---
# <a name="xsubclass-directive"></a>x:Subclass (Directiva)
Modifica el comportamiento de compilación del marcado `x:Class` XAML cuando también se proporciona. En lugar de crear una clase parcial basada en `x:Class`, el proporcionado `x:Class` se crea como una clase intermedia y, a continuación, se espera que la clase derivada proporcionada se base en `x:Class`.  
  
## <a name="xaml-attribute-usage"></a>Uso de atributos XAML  
  
```xaml  
<object x:Class="namespace.classname" x:Subclass="subclassNamespace.subclassName">  
   ...  
</object>  
```  
  
## <a name="xaml-values"></a>Valores XAML  
  
|||  
|-|-|  
|`namespace`|Opcional. Especifica un espacio de nombres CLR `classname`que contiene. Si `namespace` se especifica, un punto (.) `namespace` separa y `classname`.|  
|`classname`|Necesario. Especifica el nombre de CLR de la clase parcial que conecta el XAML cargado y el código subyacente para ese XAML. Vea la sección Comentarios.|  
|`subclassNamespace`|Opcional. Puede ser diferente de `namespace` si cada espacio de nombres puede resolver el otro. Especifica un espacio de nombres CLR `subclassName`que contiene. Si `subclassName` se especifica, un punto (.) `subclassNamespace` separa y `subclassName`.|  
|`subclassName`|Necesario. Especifica el nombre de CLR de la subclase.|  
  
## <a name="dependencies"></a>Dependencias  
 la [Directiva x:Class](x-class-directive.md) también debe proporcionarse en el mismo objeto y ese objeto debe ser el elemento raíz de la producción XAML.  
  
## <a name="remarks"></a>Comentarios  
 `x:Subclass`el uso está pensado principalmente para los lenguajes que no admiten declaraciones de clase parcial.  
  
 La clase utilizada como `x:Subclass` no puede ser una clase anidada y `x:Subclass` debe hacer referencia al objeto raíz, tal como se explica en la sección "dependencias".  
  
 De lo contrario, el significado `x:Subclass` conceptual de no está definido por una implementación de servicios .NET Framework XAML. Esto se debe a que .NET Framework comportamiento de los servicios XAML no especifica el modelo de programación general por el que se conecta el marcado XAML y el código de respaldo. Las implementaciones de más conceptos relacionados `x:Class` con `x:Subclass` y se realizan mediante marcos específicos que usan modelos de programación o modelos de aplicación para definir cómo conectar el marcado XAML, el marcado compilado y el código subyacente basado en CLR. Cada marco de trabajo puede tener sus propias acciones de compilación que habilitan parte del comportamiento o componentes específicos que se deben incluir en el entorno de compilación. Dentro de un marco de trabajo, las acciones de compilación también pueden variar en función del lenguaje CLR específico que se usa para el código subyacente.  
  
## <a name="wpf-usage-notes"></a>Notas de uso de WPF  
 `x:Subclass`puede estar en la raíz de una página o <xref:System.Windows.Application> en la raíz de la definición de la aplicación `x:Class`, que ya tiene. Al declarar `x:Class` en cualquier elemento que no sea una raíz de página o aplicación, o especificarlo donde no existe, se produce un error en tiempo de compilación. `x:Subclass`  
  
 La creación de clases derivadas que funcionan `x:Subclass` correctamente para el escenario es bastante compleja. Es posible que tenga que examinar los archivos intermedios (los archivos. g producidos en la carpeta obj del proyecto por la compilación de marcado, con los nombres que incorporan los nombres de archivo. xaml). Estos archivos intermedios pueden ayudarle a determinar el origen de ciertas construcciones de programación en las clases parciales Unidas en la aplicación compilada.  
  
 Los controladores de eventos de la clase derivada deben `internal override` ser`Friend Overrides` (en Microsoft Visual Basic) para invalidar el código auxiliar de los controladores creados en la clase intermedia durante la compilación. De lo contrario, las implementaciones de la clase derivada ocultan (prevalecen) la implementación de la clase intermedia y no se invocan los controladores de clase intermedios.  
  
 Al definir `x:Class` y `x:Subclass`, no es necesario proporcionar ninguna implementación para la clase a la `x:Class`que hace referencia. Solo tiene que asignarle un nombre a través del `x:Class` atributo para que el compilador tenga alguna orientación para la clase que crea en los archivos intermedios (el compilador no selecciona un nombre predeterminado en este caso). Puede asignar una implementación `x:Class` `x:Class` a la clase; sin embargo, este no es el escenario típico para usar y `x:Subclass`.  
  
## <a name="see-also"></a>Vea también

- [x:Class (Directiva)](x-class-directive.md)
- [Clases XAML y personalizadas para WPF](../wpf/advanced/xaml-and-custom-classes-for-wpf.md)
