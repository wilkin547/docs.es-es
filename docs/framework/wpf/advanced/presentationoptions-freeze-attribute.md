---
title: PresentationOptions:Freeze (Atributo)
ms.date: 03/30/2017
helpviewer_keywords:
- Freeze attribute [WPF]
- Freezable elements [WPF]
- PresentationOptions prefix [WPF]
ms.assetid: 391032dd-2fba-4804-bb8a-3b071797a9f4
ms.openlocfilehash: d3e0cee293a9585b972b0145da953976ed94b74c
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991428"
---
# <a name="presentationoptionsfreeze-attribute"></a>PresentationOptions:Freeze (Atributo)
Establece el <xref:System.Windows.Freezable.IsFrozen%2A> `true` estado en en el elemento <xref:System.Windows.Freezable> contenedor. El comportamiento predeterminado de <xref:System.Windows.Freezable> un sin `PresentationOptions:Freeze` el atributo especificado es <xref:System.Windows.Freezable.IsFrozen%2A> que `false` está en tiempo de carga y depende del <xref:System.Windows.Freezable> comportamiento general en tiempo de ejecución.  
  
## <a name="xaml-attribute-usage"></a>Uso de atributos XAML  
  
```xaml  
<object  
  xmlns:PresentationOptions="http://schemas.microsoft.com/winfx/2006/xaml/presentation/options"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="PresentationOptions">  
    <freezableElement PresentationOptions:Freeze="true"/>  
</object>  
```  
  
## <a name="xaml-values"></a>Valores XAML  
  
|||  
|-|-|  
|`PresentationOptions`|Un prefijo de espacio de nombres XML, que puede ser cualquier cadena de prefijo válida, según la especificación de XML 1,0. El prefijo `PresentationOptions` se usa para fines de identificación en esta documentación.|  
|`freezableElement`|Un elemento que crea una instancia de cualquier clase <xref:System.Windows.Freezable>derivada de.|  
  
## <a name="remarks"></a>Comentarios  
 El `Freeze` atributo es el único atributo u otro elemento de programación definido en `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options` el espacio de nombres XML. El `Freeze` atributo existe en este espacio de nombres especial específicamente para que se pueda designar como ignorable, mediante el [atributo MC: ignorable](mc-ignorable-attribute.md) como parte de las declaraciones del elemento raíz. La razón por `Freeze` la que se debe poder omitir es porque no todas [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] las implementaciones del procesador pueden inmovilizar <xref:System.Windows.Freezable> en tiempo de carga; esta funcionalidad no forma parte [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] de la especificación.  
  
 La capacidad de procesar el `Freeze` atributo se integra específicamente en el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] procesador que procesa [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] las aplicaciones compiladas. El atributo no es compatible con ninguna clase y la sintaxis del atributo no es extensible ni modificable. Si está implementando su propio [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] procesador, puede elegir en paralelo el comportamiento [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] de congelación del procesador al procesar `Freeze` el atributo <xref:System.Windows.Freezable> en los elementos en tiempo de carga.  
  
 Cualquier valor para el `Freeze` atributo distinto de `true` (no distingue entre mayúsculas y minúsculas) genera un error de tiempo de carga. (Especificar el `Freeze` atributo como `false` no es un error, pero ya es el valor predeterminado, por lo que establecer `false` en no hace nada).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Freezable>
- [Información general sobre objetos Freezable](freezable-objects-overview.md)
- [mc:Ignorable (atributo)](mc-ignorable-attribute.md)
