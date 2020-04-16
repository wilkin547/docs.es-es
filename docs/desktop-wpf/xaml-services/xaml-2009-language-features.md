---
title: Características del lenguaje XAML 2009
ms.date: 03/30/2017
helpviewer_keywords:
- XAML 2009 [XAML Services]
- XAML [XAML Services], XAML 2009
ms.assetid: f6bb18d8-c86a-4549-8862-323e6b32a8dd
ms.openlocfilehash: e58e6757b88958bf8a3547c8a272c2e6298dcecb
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432843"
---
# <a name="xaml-2009-language-features"></a>Características del lenguaje XAML 2009
XAML 2009 es el término abreviado para las nuevas características de lenguaje XAML que extienden la especificación del lenguaje XAML existente. XAML 2009 presenta varias nuevas directivas y construcciones. Estos incluyen la [Directiva x:Arguments](xarguments-directive.md); la [Directiva x:FactoryMethod](xfactorymethod-directive.md); la [extensión de marcado x:Reference](xreference-markup-extension.md); la [Directiva x:TypeArguments](xtypearguments-directive.md); y tipos integrados para primitivas de `x:Char`lenguaje común (por ejemplo).

## <a name="xaml-2009-support-in-wpf-and-visual-studio"></a>Soporte de XAML 2009 en WPF y Visual Studio

En WPF, puede usar características de XAML 2009 pero solo para XAML que esté compilado por marcado para WPF. El XAML compilado por marcado para WPF y el formulario BAML de XAML no admiten de momento palabras clave ni características del lenguaje XAML 2009.

Tenga en cuenta que las técnicas existentes para cargar XAML dinámico en WPF también tienen posibles restricciones de seguridad y acceso a los tipos CLR y al sistema de tipos que son más restrictivas que para XAML compilado por marcado. Para obtener más información, vea [Seguridad (WPF)](../../framework/wpf/security-wpf.md) o [Estrategia de seguridad de WPF: Seguridad de plataforma](../../framework/wpf/wpf-security-strategy-platform-security.md).

XAML 2009 también introduce otras características que modifican las construcciones de XAML 2006 anteriores o que modifican los formularios de marcado básicos.

### <a name="xkey-as-an-object-element"></a>x: Key como elemento de objeto

XAML 2009 puede admitir `x:Key` como objeto (un elemento de propiedad que tiene el valor del elemento de objeto); sin embargo, XAML 2006 solo admitía `x:Key` como atributo. Consulte la sección "XAML 2009" de [x:Key Directive](xkey-directive.md).

### <a name="xmlns-on-property-elements"></a>xmlns en elementos de propiedad

XAML 2009 puede admitir definiciones de espacio de nombres (xmlns) de XAML en elementos de propiedad; sin embargo, XAML 2006 solo admite definiciones de xmlns en elementos de objeto.

### <a name="event-attributes"></a>Atributos de eventos

En atributos respaldados por eventos, XAML 2006 presupone que la compilación de marcado está implicada y envía los eventos a la compilación de marcado. XAML 2009 admite un formato de marcado que se parece a una extensión de marcado, que pospone la conexión de eventos hasta el análisis y la carga en tiempo de ejecución de XAML. Sin embargo, las aplicaciones de WPF y los escenarios XAML para la interfaz de usuario de WPF generalmente no usan esta capacidad. WPF y su implementación de XAML 2006 usan la combinación de conexión del controlador de eventos para eventos enrutados que se definen en el nivel <xref:System.Windows.UIElement> y su paso del compilador de marcado durante gran parte del procesamiento del atributo de evento. El compilador de marcado también preprocesa los atributos de evento que se encuentren en XAML en los que las acciones de compilación declaren que se usa el compilador de marcado.

## <a name="see-also"></a>Consulte también

- [Información general sobre XAML (WPF)](../fundamentals/xaml.md)
