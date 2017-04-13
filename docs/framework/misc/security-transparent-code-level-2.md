---
title: "Security-Transparent Code, Level 2 | Microsoft Docs"
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
  - "transparency"
  - "level 2 transparency"
  - "security-transparent code"
  - "security-critical code"
ms.assetid: 4d05610a-0da6-4f08-acea-d54c9d6143c0
caps.latest.revision: 37
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 35
---
# Security-Transparent Code, Level 2
<a name="top"></a> La transparencia de nivel 2 se introdujo en [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]. Los tres principios de este modelo son código transparente, código crítico para la seguridad y disponible desde código transparente, y código crítico para la seguridad.  
  
-   El código transparente, incluido el código que se ejecuta como de plena confianza, solo puede llamar a otro código transparente o a código crítico para la seguridad y disponible desde código transparente. Solo puede realizar acciones permitidas por el conjunto de permisos de confianza parcial del dominio \(si existe\). El código transparente no puede hacer lo siguiente:  
  
    -   Realizar una instrucción <xref:System.Security.CodeAccessPermission.Assert%2A> o una elevación de privilegios.  
  
    -   Contener código no seguro o no comprobable.  
  
    -   Llamar directamente a código crítico.  
  
    -   Llamar a código nativo o código con el atributo <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute>.  
  
    -   Llamar a un miembro que está protegido por <xref:System.Security.Permissions.SecurityAction>.  
  
    -   Heredar de tipos críticos.  
  
     Además, los métodos transparentes no pueden invalidar métodos virtuales críticos o implementar métodos de interfaz críticos.  
  
-   El código crítico para la seguridad es de plena confianza, pero el código transparente puede llamarlo. Expone un área expuesta limitada de código de plena confianza; las comprobaciones de corrección y seguridad se producen en código crítico para la seguridad.  
  
-   El código crítico para la seguridad puede llamar a cualquier código y es de plena confianza, pero no se puede llamar mediante código transparente.  
  
> [!CAUTION]
>  Seguridad de acceso del código y código de confianza parcial  
>   
>  .NET Framework proporciona seguridad de acceso del código \(CAS\), que es un mecanismo para el cumplimiento de los distintos niveles de confianza en diferentes códigos que se ejecutan en la misma aplicación.  La seguridad de acceso del código en .NET Framework no debe usarse como límite de seguridad para código de confianza parcial, especialmente si se trata de código de origen desconocido. Le aconsejamos que no cargue ni ejecute código de orígenes desconocidos sin contar con medidas de seguridad alternativas.  
>   
>  Esta directiva se aplica a todas las versiones de .NET Framework, pero no se aplica a la versión de .NET Framework incluida en Silverlight.  
  
 Este tema contiene las siguientes secciones:  
  
-   [Ejemplos de uso y comportamientos](#examples)  
  
-   [Patrones de invalidación](#override)  
  
-   [Reglas de herencia](#inheritance)  
  
-   [Información y reglas adicionales](#additional)  
  
<a name="examples"></a>   
## Ejemplos de uso y comportamientos  
 Para especificar reglas de [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] \(transparencia de nivel 2\), use la siguiente anotación para un ensamblado:  
  
```  
[assembly: SecurityRules(SecurityRuleSet.Level2)]  
```  
  
 Para bloquear en las reglas de .NET Framework 2.0 \(transparencia de nivel 1\), use la siguiente anotación:  
  
```  
[assembly: SecurityRules(SecurityRuleSet.Level1)]  
```  
  
 Si no anota un ensamblado, se usan las reglas de [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] de forma predeterminada. Sin embargo, la práctica recomendada es usar el atributo <xref:System.Security.SecurityRulesAttribute> en lugar de depender del valor predeterminado.  
  
### Anotación de todo el ensamblado  
 Las reglas siguientes se aplican al uso de atributos en el nivel de ensamblado:  
  
-   Ningún atributo: si no se especifica ningún atributo, el tiempo de ejecución interpreta todo el código como crítico para la seguridad, excepto cuando por el hecho de ser crítico para la seguridad infringe una regla de herencia \(por ejemplo, al invalidar o implementar un método de interfaz o virtual transparente\). En esos casos, los métodos son críticos para la seguridad. Si no se especifica ningún atributo, Common Language Runtime determina las reglas de transparencia automáticamente.  
  
-   `SecurityTransparent`: todo el código es transparente; el ensamblado completo no hará nada que tenga privilegios o no sea seguro.  
  
-   `SecurityCritical`: todo el código introducido por tipos en este ensamblado es crítico; el código restante es transparente. Este escenario se parece a cuando no se especifica ningún atributo; sin embargo, Common Language Runtime no determina automáticamente las reglas de transparencia. Por ejemplo, si invalida un método virtual o abstracto o si implementa un método de interfaz, de forma predeterminada, ese método es transparente. Debe anotar explícitamente el método como `SecurityCritical` o `SecuritySafeCritical`; de lo contrario, se producirá una <xref:System.TypeLoadException> en tiempo de carga. Esta regla también se aplica cuando la clase base y la clase derivada están en el mismo ensamblado.  
  
-   `AllowPartiallyTrustedCallers` \(solo nivel 2\): el valor predeterminado de todo el código es transparente. Sin embargo, los miembros y tipos individuales pueden tener otros atributos.  
  
 La tabla siguiente compara el comportamiento del nivel de ensamblado de nivel 2 y nivel 1.  
  
|Assembly \(atributo\)|Nivel 2|Nivel 1|  
|---------------------------|-------------|-------------|  
|Ningún atributo en un ensamblado de confianza parcial|Los tipos y los miembros son transparentes de forma predeterminada, pero pueden ser críticos para la seguridad o bien críticos para la seguridad y disponibles desde código transparente.|Todos los tipos y los miembros son transparentes.|  
|Ningún atributo|Si no se especifica ningún atributo, Common Language Runtime determina las reglas de transparencia automáticamente. Todos los tipos y los miembros son críticos para la seguridad, excepto cuando el hecho de ser críticos para la seguridad infringe una regla de herencia.|En un ensamblado de plena confianza \(en la caché global de ensamblados, o identificado como de plena confianza en `AppDomain`\), todos los tipos son transparentes y todos los miembros son críticos para la seguridad y disponibles desde código transparente.|  
|`SecurityTransparent`|Todos los tipos y los miembros son transparentes.|Todos los tipos y los miembros son transparentes.|  
|`SecurityCritical(SecurityCriticalScope.Everything)`|No disponible.|Todos los tipos y los miembros son críticos para la seguridad.|  
|`SecurityCritical`|Todo el código introducido por tipos en este ensamblado es crítico; el código restante es transparente. Si invalida un método virtual o abstracto o si implementa un método de interfaz, debe anotar explícitamente ese método como `SecurityCritical` o `SecuritySafeCritical`.|El valor predeterminado de todo el código es transparente. Sin embargo, los miembros y tipos individuales pueden tener otros atributos.|  
  
### Anotación de tipos y de miembros  
 Los atributos de seguridad que se aplican a un tipo también se aplican a los miembros que el tipo introduce. Sin embargo, no se aplican a invalidaciones virtuales o abstractas de la clase base o implementaciones de interfaz. Las reglas siguientes se aplican al uso de atributos en el nivel de tipo y miembro:  
  
-   `SecurityCritical`: el tipo o miembro es crítico y solo lo puede invocar código de plena confianza. Los métodos que se introducen en un tipo crítico para la seguridad son críticos.  
  
    > [!IMPORTANT]
    >  Los métodos abstractos y virtuales que se introducen en interfaces o clases base y que se invalidan o se implementan en una clase crítica para la seguridad son transparentes de forma predeterminada. Se deben identificar como `SecuritySafeCritical` o `SecurityCritical`.  
  
-   `SecuritySafeCritical`: el tipo o miembro es crítico para la seguridad. Sin embargo, puede llamarse al tipo o miembro desde código transparente \(de confianza parcial\) y es tan capaz como cualquier otro código crítico. El código se debe auditar para la seguridad.  
  
 [Volver al principio](#top)  
  
<a name="override"></a>   
## Patrones de invalidación  
 La siguiente tabla muestra las invalidaciones de método permitidas para la transparencia de nivel 2.  
  
|Miembro base virtual\/de interfaz|Invalidación\/interfaz|  
|---------------------------------------|----------------------------|  
|`Transparent`|`Transparent`|  
|`Transparent`|`SafeCritical`|  
|`SafeCritical`|`Transparent`|  
|`SafeCritical`|`SafeCritical`|  
|`Critical`|`Critical`|  
  
 [Volver al principio](#top)  
  
<a name="inheritance"></a>   
## Reglas de herencia  
 En esta sección, se asigna el siguiente orden a código `Transparent`, `Critical` y `SafeCritical` en función del acceso y las capacidades:  
  
 `Transparent` \< `SafeCritical` \< `Critical`  
  
-   Reglas para tipos: van de izquierda a derecha y el acceso se vuelve más restrictivo. Los tipos derivados deben ser al menos tan restrictivos como el tipo base.  
  
-   Reglas para métodos: los métodos derivados no pueden cambiar la accesibilidad del método base. Para el comportamiento predeterminado, todos los métodos derivados no anotados son `Transparent`. Los derivados de tipos críticos provocan una excepción que se produce si el método invalidado no está anotado explícitamente como `SecurityCritical`.  
  
 En la tabla siguiente se muestran los patrones de herencia de tipo permitidos.  
  
|Clase base|La clase derivada puede ser|  
|----------------|---------------------------------|  
|`Transparent`|`Transparent`|  
|`Transparent`|`SafeCritical`|  
|`Transparent`|`Critical`|  
|`SafeCritical`|`SafeCritical`|  
|`SafeCritical`|`Critical`|  
|`Critical`|`Critical`|  
  
 En la tabla siguiente se muestran los patrones de herencia de tipo no permitidos.  
  
|Clase base|La clase derivada no puede ser|  
|----------------|------------------------------------|  
|`SafeCritical`|`Transparent`|  
|`Critical`|`Transparent`|  
|`Critical`|`SafeCritical`|  
  
 En la tabla siguiente se muestran los patrones de herencia de método permitidos.  
  
|Método base|El método derivado puede ser|  
|-----------------|----------------------------------|  
|`Transparent`|`Transparent`|  
|`Transparent`|`SafeCritical`|  
|`SafeCritical`|`Transparent`|  
|`SafeCritical`|`SafeCritical`|  
|`Critical`|`Critical`|  
  
 En la tabla siguiente se muestran los patrones de herencia de método no permitidos.  
  
|Método base|El método derivado no puede ser|  
|-----------------|-------------------------------------|  
|`Transparent`|`Critical`|  
|`SafeCritical`|`Critical`|  
|`Critical`|`Transparent`|  
|`Critical`|`SafeCritical`|  
  
> [!NOTE]
>  Estas reglas de herencia se aplican a los tipos y miembros de nivel 2. Los tipos de ensamblados de nivel 1 pueden heredar de tipos y miembros críticos para la seguridad de nivel 2. Por lo tanto, los tipos y miembros de nivel 2 deben tener peticiones de herencia independientes para los herederos de nivel 1.  
  
 [Volver al principio](#top)  
  
<a name="additional"></a>   
## Información y reglas adicionales  
  
### Compatibilidad con LinkDemand  
 El modelo de transparencia de nivel 2 reemplaza <xref:System.Security.Permissions.SecurityAction> con el atributo <xref:System.Security.SecurityCriticalAttribute>. En código heredado \(nivel 1\), <xref:System.Security.Permissions.SecurityAction> se trata automáticamente como <xref:System.Security.Permissions.SecurityAction>.  
  
### Reflexión  
 El hecho de invocar un método crítico o leer un campo crítico desencadena una petición de plena confianza \(como si se estuviera invocando un método o campo privados\). Por lo tanto, el código de plena confianza puede invocar un método crítico, mientras que el código de confianza parcial no puede.  
  
 Se han agregado las siguientes propiedades al espacio de nombres <xref:System.Reflection> para determinar si el tipo, método o campo es `SecurityCritical`, `SecuritySafeCritical` o `SecurityTransparent`: <xref:System.Type.IsSecurityCritical%2A>, <xref:System.Reflection.MethodBase.IsSecuritySafeCritical%2A> y <xref:System.Reflection.MethodBase.IsSecurityTransparent%2A>. Use estas propiedades para determinar la transparencia mediante la reflexión en lugar de comprobar la presencia del atributo. Las reglas de transparencia son complejas y la comprobación del atributo podría no ser suficiente.  
  
> [!NOTE]
>  Un método `SafeCritical` devuelve `true` para <xref:System.Type.IsSecurityCritical%2A>`` e <xref:System.Reflection.MethodBase.IsSecuritySafeCritical%2A>, ya que `SafeCritical` es crítico \(tiene las mismas capacidades que el código crítico, pero se puede llamar desde código transparente\).  
  
 Los métodos dinámicos heredan la transparencia de los módulos a los que se adjuntan; no heredan la transparencia del tipo \(si están conectados a un tipo\).  
  
### Omitir la comprobación en plena confianza  
 Puede omitir la comprobación para ensamblados transparentes de plena confianza estableciendo la propiedad <xref:System.Security.SecurityRulesAttribute.SkipVerificationInFullTrust%2A> en `true` en el atributo <xref:System.Security.SecurityRulesAttribute>:  
  
 `[assembly: SecurityRules(SecurityRuleSet.Level2, SkipVerificationInFullTrust = true)]`  
  
 La propiedad <xref:System.Security.SecurityRulesAttribute.SkipVerificationInFullTrust%2A> es `false` de forma predeterminada, por lo que la propiedad debe establecerse en `true` para omitir la comprobación. Esto debe hacerse únicamente con fines de optimización. Debe asegurarse de que el código transparente del ensamblado sea comprobable usando la opción `transparent` en la [herramienta PEVerify](../../../docs/framework/tools/peverify-exe-peverify-tool.md).  
  
## Vea también  
 [Security\-Transparent Code, Level 1](../../../docs/framework/misc/security-transparent-code-level-1.md)   
 [Cambios de seguridad](../../../docs/framework/security/security-changes.md)