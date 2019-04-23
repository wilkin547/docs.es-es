---
title: x:FieldModifier (Directiva)
ms.date: 03/30/2017
helpviewer_keywords:
- FieldModifier attribute in XAML [XAML Services]
- x:FieldModifier attribute [XAML Services]
- XAML [XAML Services], x:FieldModifier attribute
ms.assetid: ed427cd4-2f35-4d24-bd2f-0fa7b71ec248
ms.openlocfilehash: c20564bcf8a25b1b59887fbefe6419671e0d6c03
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59144552"
---
# <a name="xfieldmodifier-directive"></a>x:FieldModifier (Directiva)
Modifica el comportamiento de compilación de XAML para que se definen los campos para las referencias a objetos con nombre con <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> acceso en lugar de la <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> comportamiento predeterminado.  
  
## <a name="xaml-attribute-usage"></a>Uso de atributos XAML  
  
```xaml  
<object x:FieldModifier="Public".../>  
```  
  
## <a name="xaml-values"></a>Valores XAML  
  
|||  
|-|-|  
|*Public*|La cadena exacta que se pasa para especificar <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> frente a <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> varía según el lenguaje de programación de código subyacente que se usa. Vea la sección Comentarios.|  
  
## <a name="dependencies"></a>Dependencias  
 Si usa una producción de XAML `x:FieldModifier` en cualquier lugar, debe declarar el elemento raíz de esa producción de XAML un [x: Class directiva](x-class-directive.md).  
  
## <a name="remarks"></a>Comentarios  
 `x:FieldModifier` no es relevante para declarar el nivel de acceso general de una clase o sus miembros. Es pertinente solo para el comportamiento de procesamiento de XAML cuando se procesa un objeto XAML determinado que forma parte de una producción de XAML y se convierte en un objeto que es potencialmente accesible en el gráfico de objetos de una aplicación. De forma predeterminada, la referencia del campo para este tipo de objeto se mantiene privada, lo que impide que los consumidores del control modificando directamente el gráfico de objetos. En su lugar, los consumidores del control se deben modificar el gráfico de objetos mediante el uso de modelos estándar que están habilitados en los modelos de programación, como obtener la raíz de diseño, el elemento secundario de las colecciones de elementos, las propiedades públicas dedicadas, y así sucesivamente.  
  
 El valor de la `x:FieldModifier` atributo varía según el lenguaje de programación y su finalidad puede variar en marcos de trabajo específicos. La cadena que se va a utilizar depende de cómo cada lenguaje implementa su <xref:System.CodeDom.Compiler.CodeDomProvider> y los convertidores de tipos que devuelve para definir los significados de <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> y <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, y si dicho idioma distingue mayúsculas de minúsculas.  
  
-   Para C#, la cadena debe pasar para designar <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> es `public`.  
  
-   Para Microsoft Visual Basic. NET, la cadena debe pasar para designar <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> es `Public`.  
  
-   Para [!INCLUDE[TLA2#tla_cppcli](../../../includes/tla2sharptla-cppcli-md.md)], no existe actualmente ningún destino para XAML; por lo tanto, la cadena para pasar es indefinida.  
  
 También puede especificar <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> (`internal` en C#, `Friend` en Visual Basic), pero especificando <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> es poco común porque `NotPublic` como el comportamiento ya es la predeterminada.  
  
 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> es el comportamiento predeterminado, ya que es poco frecuente que el código fuera del ensamblado que se compila el XAML necesita acceso a un elemento XAML creada. Arquitectura de seguridad junto con el comportamiento de compilación de XAML de WPF no declarar campos que almacenan las instancias de elemento como público, a menos que se establezcan específicamente el `x:FieldModifier` para permitir el acceso público.  
  
 `x:FieldModifier` solo es pertinente para los elementos con un [x: Name Directive](x-name-directive.md) porque ese nombre se usa para hacer referencia al campo una vez es público.  
  
 De forma predeterminada, la clase parcial para el elemento raíz es pública. Sin embargo, puede hacerlo no públicos mediante el uso de la [x: ClassModifier Directive](x-classmodifier-directive.md). El [x: ClassModifier Directive](x-classmodifier-directive.md) también afecta al nivel de acceso de la instancia de la clase de elemento raíz. Puede colocar ambos `x:Name` y `x:FieldModifier` en la raíz del elemento, pero esto sólo realiza una copia de campo público del elemento raíz, con el nivel de acceso de raíz true elemento clase todavía controlada por [x: ClassModifier Directive](x-classmodifier-directive.md).  
  
## <a name="see-also"></a>Vea también

- [Clases XAML y personalizadas para WPF](../wpf/advanced/xaml-and-custom-classes-for-wpf.md)
- [Código subyacente y XAML en WPF](../wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [x:Name (Directiva)](x-name-directive.md)
- [Compilar una aplicación de WPF (WPF)](../wpf/app-development/building-a-wpf-application-wpf.md)
- [x:ClassModifier (Directiva)](x-classmodifier-directive.md)
