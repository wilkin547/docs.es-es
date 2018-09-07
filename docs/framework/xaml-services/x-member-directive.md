---
title: Directiva de x:Member
ms.date: 03/30/2017
ms.assetid: 4d8394ef-644c-4331-b6c5-be855d392980
ms.openlocfilehash: dfc08d79bd8206269807d88d2c659f13be487276
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "44064704"
---
# <a name="xmember-directive"></a>Directiva de x:Member
Declara un miembro XAML en el marcado.  
  
## <a name="xaml-object-element-usage"></a>Uso de elementos de objeto XAML  
  
```  
<object x:Class="className">  
  <x:Members>  
    <x:Member Name="propertyName"/>  
    additionalMembers  
  </x:Members>  
</object>  
```  
  
## <a name="xaml-values"></a>Valores XAML  
  
|||  
|-|-|  
|`className`|Nombre de la clase de respaldo o clase parcial para la producción de XAML.|  
|`memberName`|Nombre del miembro de la propiedad que se define.|  
  
## <a name="remarks"></a>Comentarios  
 En la implementación de servicios XAML de .NET Framework, `x:Member` no tiene un respaldo de tipos directo pero es compatible con la clase <xref:System.Windows.Markup.MemberDefinition>. En un flujo de nodo XAML, un elemento `x:Member` se representa como un miembro llamado `Member`, del espacio de nombres XAML de lenguaje XAML. El miembro `Member` contiene atributos tal y como declara el marcado.  
  
 Los significados de `Name` y `Type` no se asignan en el nivel de los servicios XAML de .NET Framework. Se almacenan en el flujo de nodo XAML inicial como valores de cadena, para ser interpretados posteriormente conforme a las reglas que puedan imponer marcos concretos. El significado puede alinearse con un nombre XAML y un significado de tipo XAML, o puede ser válido solo en un sistema de tipos de respaldo, dependiendo de la implementación.  
  
 Para admitir un uso práctico de `x:Members` como medio para especificar definiciones de miembros en el marcado, los miembros deben asociarse con una clase que se pueda modificar. El modelo previsto es que `x:Members` exista como miembro de un tipo que especifica una `x:Class`. Sin embargo, el mecanismo para asociar tipos y miembros o para generar definiciones de miembros dinámicas no se admite en el nivel de los servicios XAML de .NET Framework. De esto se encargan los marcos individuales que tienen modelos de aplicación compatibles con las definiciones de miembro de XAML. Normalmente, para admitir esta característica se necesitan acciones de compilación de MSBUILD que compilan XAML por marcado y, o bien lo integran con código subyacente o producen ensamblados puros a partir de XAML.  
  
## <a name="xproperty-for-windows-workflow-foundation"></a>x:Property para Windows Workflow Foundation  
 Para Windows Workflow Foundation, `x:Property` define los miembros de una actividad personalizada compuesta completamente en XAML o XAML, con miembros dinámicos definidos para un diseñador de actividades con código subyacente. `x:Class` también se debe especificar en el elemento raíz de la producción de XAML. Esto no es un requisito de los servicios XAML de .NET Framework, pero es obligatorio cuando la producción de XAML se carga mediante las acciones de compilación de MSBUILD que admiten actividades personalizadas y XAML en Windows Workflow Foundation en general. Windows Workflow Foundation no usa el nombre de tipo XAML puro como su valor previsto para el `x:Property` `Type` de atributo y en su lugar, utiliza una convención que no se documenta aquí. Para obtener más información, consulte [creación dinámica de la actividad](https://msdn.microsoft.com/library/dd807392.aspx).
