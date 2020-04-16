---
title: Directiva de x:Members
ms.date: 03/30/2017
ms.assetid: 155b393d-3b49-4c5a-8c9e-b3d9893af4e4
ms.openlocfilehash: c751a4f1cdea8dce7ef5165f5225ab3a825c7344
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432729"
---
# <a name="xmembers-directive"></a>Directiva de x:Members
Contiene un conjunto de miembros que se definen en el marcado, que se aplican a la x:Class del elemento primario.

## <a name="xaml-attribute-usage"></a>Uso de atributos XAML

```xaml
<object x:Class="className">
<x:Members>
  oneOrMoreMembers
</x:Members
</object>
```

## <a name="xaml-values"></a>Valores XAML

|||
|-|-|
|`className`|Nombre de la clase de respaldo o clase parcial para la producción de XAML. Vea la sección Comentarios.|
|`oneOrMoreMembers`|Uno o más elementos de objeto que representan definiciones de miembro. Normalmente, se `x:Property` trata de elementos de objeto. Vea la sección Comentarios.|

## <a name="remarks"></a>Observaciones

En la implementación de servicios XAML de .NET, `x:Members`no hay ninguna clase de respaldo o implementación de miembro subyacente para . `x:Members`es un miembro XAML especial que puede existir como miembro en cualquier tipo. En un flujo de `x:Members` nodo XAML, se `Members`representa como un miembro denominado , desde el espacio de nombres XAML del lenguaje XAML. El `Members` miembro contiene una lista `Member` genérica de objetos de solo lectura. En el marcado típico, los `x:Property` miembros individuales se especifican como elementos de propiedad. `x:Property`es un tipo más preciso específicamente para las `x:Member`propiedades de los tipos y es asignable a . Para obtener más información, vea [x:Property Directive](xproperty-directive.md).

Para admitir un uso práctico de `x:Members` como medio para especificar definiciones de miembros en el marcado, los miembros deben asociarse con una clase que se pueda modificar. El modelo previsto es que `x:Members` exista como miembro de un tipo que especifica una `x:Class`. Sin embargo, el mecanismo para asociar tipos y miembros o para producir definiciones de miembros dinámicos no se admite en el nivel de servicios XAML de .NET. De esto se encargan los marcos individuales que tienen modelos de aplicación compatibles con las definiciones de miembro de XAML. Normalmente, para admitir esta característica se necesitan acciones de compilación de MSBUILD que compilan XAML por marcado y, o bien lo integran con código subyacente o producen ensamblados puros a partir de XAML.

## <a name="xmembers-for-windows-workflow-foundation"></a>x:Miembros de Windows Workflow Foundation

Para Windows Workflow `x:Members` Foundation, contiene los miembros de una actividad personalizada compuesta por completo en XAML o miembros dinámicos definidos por XAML para un diseñador de actividades con código subyacente. `x:Class` también se debe especificar en el elemento raíz de la producción de XAML. Esto no es un requisito en el nivel de servicios XAML de .NET, pero se convierte en un requisito cuando la producción XAML se carga mediante las acciones de compilación de MSBUILD que admiten actividades personalizadas y XAML de Windows Workflow Foundation en general. `x:Members`debe ser el primer elemento secundario en el `x:Class`marcado del elemento de objeto que declara el archivo .
