---
title: "x:Members Directive | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 155b393d-3b49-4c5a-8c9e-b3d9893af4e4
caps.latest.revision: 5
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 5
---
# x:Members Directive
Contiene un conjunto de miembros definidos en el marcado, que se aplican al elemento primario x:Class.  
  
## Uso de atributos XAML  
  
```  
  
<object x:Class="className">  
  <x:Members>  
    oneOrMoreMembers  
  </x:Members  
</object>  
```  
  
## Valores XAML  
  
|||  
|-|-|  
|`className`|Nombre de la clase de respaldo o la clase parcial para la producción XAML.  Vea la sección Comentarios.|  
|`oneOrMoreMembers`|Uno o más elementos del objeto que representan las definiciones de miembro.  Normalmente, estos son elementos de objeto `x:Property`.  Vea la sección Comentarios.|  
  
## Comentarios  
 En la implementación de los servicios XAML de .NET Framework, no hay ninguna clase de respaldo o implementación de miembro subyacente para `x:Members`.  `x:Members` es un miembro XAML especial que puede existir como miembro en cualquier tipo.  En un flujo de nodo XAML, `x:Members` se representa como miembro denominado `Members`, del espacio de nombres XAML del lenguaje XAML.  El miembro `Members` contiene una lista genérica de solo lectura de objetos `Member`.  En el marcado típico, los miembros individuales se especifican como elementos de la propiedad `x:Property`.  `x:Property` es un tipo más preciso específicamente para las propiedades de los tipos y es asignable a `x:Member`.  Para obtener más información, vea [x:Property Directive](../../../docs/framework/xaml-services/x-property-directive.md).  
  
 Para poder usar `x:Members` de forma práctica para especificar las definiciones de miembro en el marcado, los miembros deben asociarse a una clase que se pueda modificar.  El modelo previsto es que `x:Members` existe como miembro de un tipo que especifica una `x:Class`.  Sin embargo, el mecanismo para asociar tipos y miembros, o las definiciones de compilación dinámicas de los miembros no es compatible con el porcentaje de disponibilidad XAML de .NET Framework.  Esto se deja para los marcos individuales con modelos de aplicación que admiten las definiciones de miembro de XAML.  Normalmente, las acciones de compilación de MSBUILD que marcan o compilan el XAML y lo integran con código subyacente o producen ensamblados de XAML puros son necesarias para admitir esa característica.  
  
## x:Members para Windows Workflow Foundation  
 Para Windows Workflow Foundation, `x:Members` contiene los miembros de una actividad personalizada compuesta completamente en XAML o los miembros dinámicos definidos en XAML para un diseñador de actividades con código subyacente.  `x:Class` también se debe especificar en el elemento raíz de la producción XAML.  Este no es un requisito en el nivel de servicios XAML de .NET Framework, pero se convierte en requisito cuando las acciones de compilación de MSBUILD que admiten actividades personalizadas y el XAML de Windows Workflow Foundation XAML en general cargan la producción XAML.  `x:Members` debe ser el primer elemento secundario en el marcado del elemento de objeto que declara `x:Class`.