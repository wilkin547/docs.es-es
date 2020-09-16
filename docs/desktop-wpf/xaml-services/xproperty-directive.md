---
title: Directiva de x:Property
ms.date: 03/30/2017
ms.assetid: 618555a8-c893-455c-810f-ac54cd24ef10
ms.openlocfilehash: d4294b39ff262198f8082863d23eb6f4edbc7054
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90549306"
---
# <a name="xproperty-directive"></a>Directiva de x:Property

Declara una propiedad XAML en el marcado.

## <a name="xaml-object-element-usage"></a>Uso de elementos de objeto XAML

```xaml
<object x:Class="className">
  <x:Members>
    <x:Property Name="propertyName" Type="propertyType"/>
    additionalProperties
  </x:Members>
</object>
```

## <a name="xaml-values"></a>Valores XAML

|||
|-|-|
|`className`|Nombre de la clase de respaldo o clase parcial para la producción de XAML.|
|`propertyName`|Nombre del miembro de la propiedad que se define.|
|`propertyType`|Nombre del tipo (u otra forma de cadena, específica del marco) que especifica el tipo de esta propiedad.|

## <a name="remarks"></a>Comentarios

En la implementación de servicios XAML de .NET,. `x:Property` no tiene un respaldo de tipos directo pero es compatible con la clase <xref:System.Windows.Markup.PropertyDefinition>. En un flujo de nodo XAML, un elemento `x:Property` se representa como un miembro llamado `Property`, del espacio de nombres XAML de lenguaje XAML. El miembro `Property` contiene atributos tal y como declara el marcado.

El significado de `Name` y `Type` no se asigna en el nivel de servicios XAML de .net. Se almacenan en el flujo de nodo XAML inicial como valores de cadena, para ser interpretados posteriormente conforme a las reglas que puedan imponer marcos concretos. El significado puede alinearse con un nombre XAML y un significado de tipo XAML, o puede ser válido solo en un sistema de tipos de respaldo, dependiendo de la implementación.

Para admitir un uso práctico de `x:Members` como medio para especificar definiciones de miembros en el marcado, los miembros deben asociarse con una clase que se pueda modificar. El modelo previsto es que `x:Members` exista como miembro de un tipo que especifica una `x:Class`. Sin embargo, el mecanismo para asociar tipos y miembros o para producir definiciones de miembros dinámicos no se admite en el nivel de servicios XAML de .NET. De esto se encargan los marcos individuales que tienen modelos de aplicación compatibles con las definiciones de miembro de XAML. Normalmente, para admitir esta característica se necesitan acciones de compilación de MSBUILD que compilan XAML por marcado y, o bien lo integran con código subyacente o producen ensamblados puros a partir de XAML.

## <a name="xproperty-for-windows-workflow-foundation"></a>x:Property para Windows Workflow Foundation

Para Windows Workflow Foundation, `x:Property` define los miembros de una actividad personalizada compuesta completamente en XAML o XAML, con miembros dinámicos definidos para un diseñador de actividades con código subyacente. `x:Class` también se debe especificar en el elemento raíz de la producción de XAML. Esto no es un requisito en el nivel de servicios XAML de .NET, pero se convierte en un requisito cuando la producción de XAML se carga mediante las acciones de compilación de MSBUILD que admiten las actividades personalizadas y Windows Workflow Foundation XAML en general. Windows Workflow Foundation no utiliza el nombre de tipo XAML puro como valor previsto para el `x:Property` `Type` atributo y, en su lugar, utiliza una Convención que no se documenta aquí. Para obtener más información, vea [creación de DynamicActivity](/previous-versions/dotnet/netframework-4.0/dd807392(v=vs.100)).
