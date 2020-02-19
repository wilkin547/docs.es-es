---
title: Interoperabilidad COM en aplicaciones .NET Framework
ms.date: 07/20/2015
helpviewer_keywords:
- interoperability, COM and .NET Framework objects
- COM interop [Visual Basic]
- shared components
ms.assetid: f5a72143-c268-4dff-a019-974ad940e17d
ms.openlocfilehash: c3567464616d3b0b3f91ff57e8a169aca046c866
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452297"
---
# <a name="com-interoperability-in-net-framework-applications-visual-basic"></a>Interoperabilidad COM en aplicaciones .NET Framework (Visual Basic)

Si desea usar objetos COM y .NET Framework objetos en la misma aplicación, debe abordar las diferencias en la forma en que los objetos existen en la memoria. Un objeto de .NET Framework se encuentra en la memoria administrada (la memoria controlada por el Common Language Runtime) y puede moverse por el tiempo de ejecución según sea necesario. Un objeto COM se encuentra en la memoria no administrada y no se espera que se mueva a otra ubicación de memoria. Visual Studio y el .NET Framework proporcionan herramientas para controlar la interacción de estos componentes administrados y no administrados. Para obtener más información sobre el código administrado, vea [Common Language Runtime](../../../standard/clr.md).

Además de usar objetos COM en aplicaciones .NET, puede que también desee usar Visual Basic para desarrollar objetos accesibles desde código no administrado a través de COM.

Los vínculos de esta página proporcionan detalles sobre las interacciones entre los objetos COM y .NET Framework.

## <a name="related-sections"></a>Secciones relacionadas

| | |
|---------|---------|
| [Interoperabilidad COM](../../../visual-basic/programming-guide/com-interop/index.md) | Proporciona vínculos a temas que tratan sobre la interoperabilidad COM en Visual Basic, incluidos objetos COM, controles ActiveX, archivos dll de Win32, objetos administrados y herencia de objetos COM. |
| [Interoperating with Unmanaged Code](../../../framework/interop/index.md) (Interoperar con código no administrado) | Describe brevemente algunos de los problemas de interacción entre el código administrado y no administrado, y proporciona vínculos para seguir estudiando. |
| [Contenedores COM](../../../standard/native-interop/com-wrappers.md) | Describe los contenedores a los que se puede llamar en tiempo de ejecución, que permiten que el código administrado llame a métodos COM, y a contenedores COM Invocables, que permiten a los clientes COM llamar a métodos de objeto .NET. |
| [Interoperabilidad COM avanzada](../../../framework/interop/index.md) | Proporciona vínculos a temas que tratan sobre la interoperabilidad COM con respecto a contenedores, excepciones, herencia, subprocesamiento, eventos, conversiones y serialización. |
| [TlbImp.exe (Importador de la biblioteca de tipos)](../../../framework/tools/tlbimp-exe-type-library-importer.md) | Describe la herramienta que se puede usar para convertir las definiciones de tipos que se encuentran en una biblioteca de tipos COM en definiciones equivalentes en un ensamblado de Common Language Runtime. |
