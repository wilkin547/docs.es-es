---
title: PresentationOptions:Freeze (Atributo)
ms.date: 03/30/2017
helpviewer_keywords:
- Freeze attribute [WPF]
- Freezable elements [WPF]
- PresentationOptions prefix [WPF]
ms.assetid: 391032dd-2fba-4804-bb8a-3b071797a9f4
ms.openlocfilehash: e60c4a505db42936f188354f52edd7832fb9632b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59074669"
---
# <a name="presentationoptionsfreeze-attribute"></a>PresentationOptions:Freeze (Atributo)
Establece el <xref:System.Windows.Freezable.IsFrozen%2A> estado `true` en el que contiene <xref:System.Windows.Freezable> elemento. Comportamiento predeterminado de un <xref:System.Windows.Freezable> sin el `PresentationOptions:Freeze` atributo especificado que es <xref:System.Windows.Freezable.IsFrozen%2A> es `false` en tiempo de carga y depende del general <xref:System.Windows.Freezable> comportamiento en tiempo de ejecución.  
  
## <a name="xaml-attribute-usage"></a>Uso de atributos XAML  
  
```  
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
|`PresentationOptions`|Un prefijo de espacio de nombres XML, que puede ser cualquier cadena de prefijo válido, según la especificación XML 1.0. El prefijo `PresentationOptions` se usa para propósitos de identificación en esta documentación.|  
|`freezableElement`|Un elemento que crea una instancia de cualquier clase derivada de <xref:System.Windows.Freezable>.|  
  
## <a name="remarks"></a>Comentarios  
 El `Freeze` es el único atributo o de otro elemento de programación definidos en el `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options` espacio de nombres XML. El `Freeze` atributo existe en este espacio de nombres especial específicamente para que pueden designarse como ignorable, mediante [mc: Ignorable (atributo)](mc-ignorable-attribute.md) como parte de las declaraciones del elemento raíz. La razón por la que `Freeze` debe ser capaz de se puede pasar por alto es porque no todos los [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] las implementaciones de procesadores pueden inmovilizar un <xref:System.Windows.Freezable> en tiempo de carga; esta funcionalidad no está forma parte de la [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] especificación.  
  
 La capacidad para procesar el `Freeze` atributo específicamente integrado en el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] procesador que procesa [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] para aplicaciones compiladas. El atributo no es compatible con cualquier clase, y la sintaxis de atributo no es extensible o modificable. Si está implementando su propio [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] procesador puede elegir el comportamiento de bloqueo en paralelo el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] procesador al procesar el `Freeze` atributo <xref:System.Windows.Freezable> elementos en tiempo de carga.  
  
 Cualquier valor para el `Freeze` atributo distinto `true` (no distingue mayúsculas de minúsculas) genera un error en tiempo de carga. (Especificar la `Freeze` atributo como `false` no es un error, pero que ya es el predeterminado, por lo que si se establece en `false` no hace nada).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Freezable>
- [Información general sobre objetos Freezable](freezable-objects-overview.md)
- [Atributo mc:Ignorable](mc-ignorable-attribute.md)
