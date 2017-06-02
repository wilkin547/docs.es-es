---
title: "Qualifying .NET Types for Interoperation | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "exposing .NET Framework components to COM"
  - "COM interop, qualifying .NET types"
  - "qualifying .NET types for interoperation"
  - "interoperation with unmanaged code, qualifying .NET types"
  - "interoperation with unmanaged code, exposing .NET Framework components"
  - "COM interop, exposing COM components"
ms.assetid: 4b8afb52-fb8d-4e65-b47c-fd82956a3cdd
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# Qualifying .NET Types for Interoperation
Si va a exponer los tipos de un ensamblado en aplicaciones COM, tenga en cuenta los requisitos de la interoperabilidad COM en tiempo de diseño.  Los tipos administrados \(clase, interfaz, estructura y enumeración\) se integran a la perfección con los tipos COM si se cumplen las directrices siguientes:  
  
-   Las clases deben implementar las interfaces de forma explícita.  
  
     Si bien la interoperabilidad COM proporciona un mecanismo para generar automáticamente una interfaz con todos los miembros de la clase y los miembros de su clase base, es mucho mejor proporcionar interfaces explícitas.  La interfaz generada de forma automática se denomina interfaz de clase.  Para obtener instrucciones, vea [Presentar la interfaz de clase](http://msdn.microsoft.com/es-es/733c0dd2-12e5-46e6-8de1-39d5b25df024).  
  
     Puede usar [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], C\# y C\+\+ para incorporar las definiciones de interfaz en el código, en vez de tener que utilizar el lenguaje de definición de interfaz \(IDL\) o su equivalente.  Para obtener información detallada sobre la sintaxis, consulte la documentación del lenguaje.  
  
-   Los tipos administrados deben ser públicos.  
  
     Sólo se registran y se exportan a la biblioteca de tipos los tipos públicos de un ensamblado.  Como consecuencia, sólo son visibles para COM los tipos públicos.  
  
     Los tipos administrados exponen características en otro código administrado que podría no exponerse en COM.  Por ejemplo, los constructores con parámetros, los métodos estáticos y los campos constantes no se exponen en los clientes COM.  Además, mientras el motor de tiempo de ejecución calcula las referencias de datos dentro y fuera de un tipo, puede ocurrir que los datos se copien o se transformen.  
  
-   Los métodos, propiedades, campos y eventos deben ser públicos.  
  
     Los miembros de tipos públicos han de ser públicos también a fin de que sean visibles para COM.  Puede restringirse la visibilidad de un ensamblado, un tipo público o miembros públicos de un tipo público aplicando <xref:System.Runtime.InteropServices.ComVisibleAttribute>.  De forma predeterminada, todos los tipos y miembros públicos son visibles.  
  
-   Los tipos deben tener un constructor público predeterminado que se active desde COM.  
  
     Los tipos públicos administrados son visibles para COM.  Sin embargo, sin un constructor público predeterminado \(un constructor sin argumentos\), los clientes COM no pueden crear el tipo.  Los clientes COM pueden, a pesar de todo, utilizar el tipo si se activa por otros medios.  
  
-   Los tipos no pueden ser abstractos.  
  
     Ni los clientes COM ni los clientes .NET pueden crear tipos abstractos.  
  
 Cuando se exporta a COM, la jerarquía de herencia de un tipo administrado se elimina.  El control de versiones también es distinto en función de que el entorno sea administrado o no administrado.  Los tipos expuestos a COM no tienen las mismas características de control de versiones que otros tipos administrados.  
  
## Vea también  
 <xref:System.Runtime.InteropServices.ComVisibleAttribute>   
 [Exposing .NET Framework Components to COM](../../../docs/framework/interop/exposing-dotnet-components-to-com.md)   
 [Introducing the Class Interface](http://msdn.microsoft.com/es-es/733c0dd2-12e5-46e6-8de1-39d5b25df024)   
 [Applying Interop Attributes](../../../docs/framework/interop/applying-interop-attributes.md)   
 [Packaging an Assembly for COM](../../../docs/framework/interop/packaging-an-assembly-for-com.md)