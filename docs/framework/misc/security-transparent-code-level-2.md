---
title: Código transparente en seguridad, nivel 2
description: Comprenda el código transparente de nivel 2. Vea ejemplos de uso y comportamientos, invalidar patrones, reglas de herencia, etc.
ms.date: 03/30/2017
helpviewer_keywords:
- transparency
- level 2 transparency
- security-transparent code
- security-critical code
ms.assetid: 4d05610a-0da6-4f08-acea-d54c9d6143c0
ms.openlocfilehash: bbff7b53bacd50746de56c8dba85cdc9e4b1ad9b
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556413"
---
# <a name="security-transparent-code-level-2"></a>Código transparente en seguridad, nivel 2

[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]

La transparencia de nivel 2 se presentó en el .NET Framework 4. Los tres principios de este modelo son código transparente, código crítico para la seguridad y disponible desde código transparente, y código crítico para la seguridad.

- El código transparente, incluido el código que se ejecuta como de plena confianza, solo puede llamar a otro código transparente o a código crítico para la seguridad y disponible desde código transparente. Solo puede realizar acciones permitidas por el conjunto de permisos de confianza parcial del dominio (si existe). El código transparente no puede hacer lo siguiente:

  - Realizar una instrucción <xref:System.Security.CodeAccessPermission.Assert%2A> o una elevación de privilegios.

  - Contener código no seguro o no comprobable.

  - Llamar directamente a código crítico.

  - Llamar a código nativo o código con el atributo <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute>.

  - Llamar a un miembro que está protegido por <xref:System.Security.Permissions.SecurityAction.LinkDemand>.

  - Heredar de tipos críticos.

  Además, los métodos transparentes no pueden invalidar métodos virtuales críticos o implementar métodos de interfaz críticos.

- El código crítico para la seguridad es de plena confianza, pero el código transparente puede llamarlo. Expone un área expuesta limitada de código de plena confianza; las comprobaciones de corrección y seguridad se producen en código crítico para la seguridad.

- El código crítico para la seguridad puede llamar a cualquier código y es de plena confianza, pero no se puede llamar mediante código transparente.

## <a name="usage-examples-and-behaviors"></a>Ejemplos de uso y comportamientos

Para especificar .NET Framework 4 reglas (transparencia de nivel 2), use la siguiente anotación para un ensamblado:

```csharp
[assembly: SecurityRules(SecurityRuleSet.Level2)]
```

Para bloquear en las reglas de .NET Framework 2.0 (transparencia de nivel 1), use la siguiente anotación:

```csharp
[assembly: SecurityRules(SecurityRuleSet.Level1)]
```

Si no anota un ensamblado, se usan las reglas de .NET Framework 4 de forma predeterminada. Sin embargo, el procedimiento recomendado es usar el <xref:System.Security.SecurityRulesAttribute> atributo en lugar de depender del valor predeterminado.

### <a name="assembly-wide-annotation"></a>Anotación de todo el ensamblado

Las reglas siguientes se aplican al uso de atributos en el nivel de ensamblado:

- Ningún atributo: si no se especifica ningún atributo, el tiempo de ejecución interpreta todo el código como crítico para la seguridad, excepto cuando por el hecho de ser crítico para la seguridad infringe una regla de herencia (por ejemplo, al invalidar o implementar un método de interfaz o virtual transparente). En esos casos, los métodos son críticos para la seguridad. Si no se especifica ningún atributo, Common Language Runtime determina las reglas de transparencia automáticamente.

- `SecurityTransparent`: todo el código es transparente; el ensamblado completo no hará nada que tenga privilegios o no sea seguro.

- `SecurityCritical`: todo el código introducido por tipos en este ensamblado es crítico; el código restante es transparente. Este escenario se parece a cuando no se especifica ningún atributo; sin embargo, Common Language Runtime no determina automáticamente las reglas de transparencia. Por ejemplo, si invalida un método virtual o abstracto o si implementa un método de interfaz, de forma predeterminada, ese método es transparente. Debe anotar explícitamente el método como `SecurityCritical` o `SecuritySafeCritical`; de lo contrario, se producirá una <xref:System.TypeLoadException> en tiempo de carga. Esta regla también se aplica cuando la clase base y la clase derivada están en el mismo ensamblado.

- `AllowPartiallyTrustedCallers` (solo nivel 2): el valor predeterminado de todo el código es transparente. Sin embargo, los miembros y tipos individuales pueden tener otros atributos.

En la tabla siguiente se compara el comportamiento de nivel de ensamblado para el nivel 2 con el nivel 1.

|Atributo de ensamblado|Nivel 2|Nivel 1|
|------------------------|-------------|-------------|
|Ningún atributo en un ensamblado de confianza parcial|Los tipos y los miembros son transparentes de forma predeterminada, pero pueden ser críticos para la seguridad o bien críticos para la seguridad y disponibles desde código transparente.|Todos los tipos y los miembros son transparentes.|
|Ningún atributo|Si no se especifica ningún atributo, Common Language Runtime determina las reglas de transparencia automáticamente. Todos los tipos y los miembros son críticos para la seguridad, excepto cuando el hecho de ser críticos para la seguridad infringe una regla de herencia.|En un ensamblado de plena confianza (en la caché global de ensamblados, o identificado como de plena confianza en `AppDomain`), todos los tipos son transparentes y todos los miembros son críticos para la seguridad y disponibles desde código transparente.|
|`SecurityTransparent`|Todos los tipos y los miembros son transparentes.|Todos los tipos y los miembros son transparentes.|
|`SecurityCritical(SecurityCriticalScope.Everything)`|No aplicable.|Todos los tipos y los miembros son críticos para la seguridad.|
|`SecurityCritical`|Todo el código introducido por tipos en este ensamblado es crítico; el código restante es transparente. Si invalida un método virtual o abstracto o si implementa un método de interfaz, debe anotar explícitamente ese método como `SecurityCritical` o `SecuritySafeCritical`.|El valor predeterminado de todo el código es transparente. Sin embargo, los miembros y tipos individuales pueden tener otros atributos.|

### <a name="type-and-member-annotation"></a>Anotación de tipos y de miembros

Los atributos de seguridad que se aplican a un tipo también se aplican a los miembros que el tipo introduce. Sin embargo, no se aplican a invalidaciones virtuales o abstractas de la clase base o implementaciones de interfaz. Las reglas siguientes se aplican al uso de atributos en el nivel de tipo y miembro:

- `SecurityCritical`: el tipo o miembro es crítico y solo lo puede invocar código de plena confianza. Los métodos que se introducen en un tipo crítico para la seguridad son críticos.

    > [!IMPORTANT]
    > Los métodos abstractos y virtuales que se introducen en interfaces o clases base y que se invalidan o se implementan en una clase crítica para la seguridad son transparentes de forma predeterminada. Se deben identificar como `SecuritySafeCritical` o `SecurityCritical`.

- `SecuritySafeCritical`: el tipo o miembro es crítico para la seguridad. Sin embargo, puede llamarse al tipo o miembro desde código transparente (de confianza parcial) y es tan capaz como cualquier otro código crítico. El código se debe auditar para la seguridad.

## <a name="override-patterns"></a>Patrones de invalidación

La siguiente tabla muestra las invalidaciones de método permitidas para la transparencia de nivel 2.

|Miembro base virtual/de interfaz|Invalidación/interfaz|
|------------------------------------|-------------------------|
|`Transparent`|`Transparent`|
|`Transparent`|`SafeCritical`|
|`SafeCritical`|`Transparent`|
|`SafeCritical`|`SafeCritical`|
|`Critical`|`Critical`|

## <a name="inheritance-rules"></a>Reglas de herencia

En esta sección, se asigna el siguiente orden a código `Transparent`, `Critical` y `SafeCritical` en función del acceso y las capacidades:

`Transparent` < `SafeCritical` < `Critical`

- Reglas para tipos: van de izquierda a derecha y el acceso se vuelve más restrictivo. Los tipos derivados deben ser al menos tan restrictivos como el tipo base.

- Reglas para métodos: los métodos derivados no pueden cambiar la accesibilidad del método base. Para el comportamiento predeterminado, todos los métodos derivados no anotados son `Transparent`. Los derivados de tipos críticos provocan una excepción que se produce si el método invalidado no está anotado explícitamente como `SecurityCritical`.

En la tabla siguiente se muestran los patrones de herencia de tipo permitidos.

|Clase base|La clase derivada puede ser|
|----------------|--------------------------|
|`Transparent`|`Transparent`|
|`Transparent`|`SafeCritical`|
|`Transparent`|`Critical`|
|`SafeCritical`|`SafeCritical`|
|`SafeCritical`|`Critical`|
|`Critical`|`Critical`|

En la tabla siguiente se muestran los patrones de herencia de tipo no permitidos.

|Clase base|La clase derivada no puede ser|
|----------------|-----------------------------|
|`SafeCritical`|`Transparent`|
|`Critical`|`Transparent`|
|`Critical`|`SafeCritical`|

En la tabla siguiente se muestran los patrones de herencia de método permitidos.

|Método base|El método derivado puede ser|
|-----------------|---------------------------|
|`Transparent`|`Transparent`|
|`Transparent`|`SafeCritical`|
|`SafeCritical`|`Transparent`|
|`SafeCritical`|`SafeCritical`|
|`Critical`|`Critical`|

En la tabla siguiente se muestran los patrones de herencia de método no permitidos.

|Método base|El método derivado no puede ser|
|-----------------|------------------------------|
|`Transparent`|`Critical`|
|`SafeCritical`|`Critical`|
|`Critical`|`Transparent`|
|`Critical`|`SafeCritical`|

> [!NOTE]
> Estas reglas de herencia se aplican a los tipos y miembros de nivel 2. Los tipos de ensamblados de nivel 1 pueden heredar de tipos y miembros críticos para la seguridad de nivel 2. Por lo tanto, los tipos y miembros de nivel 2 deben tener peticiones de herencia independientes para los herederos de nivel 1.

## <a name="additional-information-and-rules"></a>Información y reglas adicionales

### <a name="linkdemand-support"></a>Compatibilidad con LinkDemand

El modelo de transparencia de nivel 2 reemplaza <xref:System.Security.Permissions.SecurityAction.LinkDemand> con el atributo <xref:System.Security.SecurityCriticalAttribute>. En código heredado (nivel 1), <xref:System.Security.Permissions.SecurityAction.LinkDemand> se trata automáticamente como <xref:System.Security.Permissions.SecurityAction.Demand>.

### <a name="reflection"></a>Reflexión

El hecho de invocar un método crítico o leer un campo crítico desencadena una petición de plena confianza (como si se estuviera invocando un método o campo privados). Por lo tanto, el código de plena confianza puede invocar un método crítico, mientras que el código de confianza parcial no puede.

Se han agregado las siguientes propiedades al espacio de nombres <xref:System.Reflection> para determinar si el tipo, método o campo es `SecurityCritical`, `SecuritySafeCritical` o `SecurityTransparent`: <xref:System.Type.IsSecurityCritical%2A>, <xref:System.Reflection.MethodBase.IsSecuritySafeCritical%2A> y <xref:System.Reflection.MethodBase.IsSecurityTransparent%2A>. Use estas propiedades para determinar la transparencia mediante la reflexión en lugar de comprobar la presencia del atributo. Las reglas de transparencia son complejas y la comprobación del atributo podría no ser suficiente.

> [!NOTE]
> Un `SafeCritical` método devuelve `true` para <xref:System.Type.IsSecurityCritical%2A> y <xref:System.Reflection.MethodBase.IsSecuritySafeCritical%2A> , porque `SafeCritical` es realmente crítico (tiene las mismas funcionalidades que el código crítico, pero se puede llamar desde código transparente).

Los métodos dinámicos heredan la transparencia de los módulos a los que se adjuntan; no heredan la transparencia del tipo (si están conectados a un tipo).

### <a name="skip-verification-in-full-trust"></a>Omitir la comprobación en plena confianza

Puede omitir la comprobación para ensamblados transparentes de plena confianza estableciendo la propiedad <xref:System.Security.SecurityRulesAttribute.SkipVerificationInFullTrust%2A> en `true` en el atributo <xref:System.Security.SecurityRulesAttribute>:

`[assembly: SecurityRules(SecurityRuleSet.Level2, SkipVerificationInFullTrust = true)]`

La propiedad <xref:System.Security.SecurityRulesAttribute.SkipVerificationInFullTrust%2A> es `false` de forma predeterminada, por lo que la propiedad debe establecerse en `true` para omitir la comprobación. Esto debe hacerse únicamente con fines de optimización. Debe asegurarse de que el código transparente del ensamblado se puede comprobar mediante la `transparent` opción de la [herramienta peverify](../tools/peverify-exe-peverify-tool.md).

## <a name="see-also"></a>Vea también

- [Código transparente en seguridad, nivel 1](security-transparent-code-level-1.md)
- [Cambios de seguridad](/previous-versions/dotnet/framework/security/security-changes)
