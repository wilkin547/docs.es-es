---
title: "Cambios en tiempo de ejecución en .NET Framework 4.7 | Microsoft Docs"
ms.custom: 
ms.date: 04/07/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- runtime changes,.NET Framework
- runtime changes,.NET Framework 4.7
- application compatibility
ms.assetid: 268eb334-7906-4e0b-a1e3-c74b745de2a5
caps.latest.revision: 8
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 321ec8f8293afad0f3da7fb6f907f45d404394cc
ms.contentlocale: es-es
ms.lasthandoff: 04/18/2017

---
# <a name="runtime-changes-in-the-net-framework-47"></a>Cambios en tiempo de ejecución en .NET Framework 4.7

En casos poco frecuentes, los cambios en tiempo de ejecución pueden afectar a las aplicaciones existentes que tienen como destino versiones anteriores de .NET Framework, pero que se ejecutan en una versión posterior del tiempo de ejecución de .NET Framework. También conllevan comportamientos diferentes en las aplicaciones que se ejecutan en distintos entornos en tiempo de ejecución de .NET Framework. .NET Framework 4.6.2 incluye cambios en las áreas siguientes:

- [Windows Presentation Foundation (WPF)](#WPF)

La columna de ámbito de las tablas siguientes especifica la importancia de cada cambio:

- Principal. Cambio significativo que afecta a un gran número de aplicaciones o que requiere una modificación sustancial del código. Observe que ninguno de los cambios de redestinación pertenecen a esta categoría.

- Secundario. Cambio que afecta a un pequeño número de aplicaciones o que requiere ligeras modificaciones en el código.

- Avanzado. Cambio que afecta a aplicaciones de escenarios muy concretos que no son frecuentes.

- Transparente. Cambio que no tiene ningún efecto apreciable en el programador o el usuario de la aplicación. No es necesario modificar la aplicación debido a este cambio.

## <a name="a-namewpf--windows-presentation-foundation-wpf"></a><a name="WPF" /> Windows Presentation Foundation (WPF)

assetId:///M:System.Windows.Controls.DataGridCellsPanel.BringIndexIntoView(System.Int32)?qualifyHint=False&autoUpgrade=True

| Característica | Cambio | Impacto | Ámbito |
|---|---|---|---|
| <xref:System.Windows.Controls.DataGridCellsPanel.BringIndexIntoView%2A> method | En .NET Framework 4.6.2, el método <xref:System.Windows.Controls.DataGridCellsPanel.BringIndexIntoView%2A> se ejecuta de forma asíncrona cuando se habilite la virtualización de columnas, pero el ancho de las columnas no se haya determinado. Si se quitan las columnas antes de que se complete la operación asíncrona, puede producirse un elemento <xref:System.ArgumentOutOfRangeException>.<br/></br>A partir de .NET Framework 4.7, no se genera la excepción en este escenario. | Este cambio mejora la confiabilidad del método. | Borde | 
|Fondo <xref:System.Windows.Controls.Ribbon.RibbonGroup> | En .NET Framework 4.6.2 y versiones anteriores, el fondo <xref:System.Windows.Controls.Ribbon.RibbonGroup> en las compilaciones localizadas se pintó con una brocha transparente, lo que provocó una experiencia de la interfaz de usuario deficiente. En .NET Framework 4.7, WPF actualizó los recursos localizados para el control <xref:System.Windows.Controls.Ribbon.RibbonGroup>, lo que garantiza que se ha seleccionado la brocha correcta. | Para sacar provecho del nuevo comportamiento, actualice a .NET Framework 4.7. | Borde |
| Corrector ortográfico de WPF | A partir de .NET Framework 4.6.1, el corrector ortográfico en aplicaciones de WPF normalmente genera un elemento <xref:System.ObjectDisposedException> durante el apagado de la aplicación. <br/><br/>En .NET Framework 4.7, la excepción se controla correctamente mediante el tiempo de ejecución, lo que garantiza que las aplicaciones ya no se ven afectadas. Debe tenerse en cuenta que se siguen observando excepciones ocasionales por primera vez en aplicaciones que se ejecutan con un depurador.  | Para sacar provecho del nuevo comportamiento, actualice a .NET Framework 4.7.   | Borde |

## <a name="see-also"></a>Vea también

[Compatibilidad de aplicaciones en .NET Framework 4.7](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-7.md)


