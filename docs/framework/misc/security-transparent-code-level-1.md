---
title: Código transparente en seguridad, nivel 1
description: Revise los ejemplos de modelo de código de transparencia de nivel 1, atributos de transparencia y transparencia de seguridad.
ms.date: 03/30/2017
helpviewer_keywords:
- transparent
- SecurityTreatAsSafeAttribute
- SecurityTransparentAttribute
- SecurityCriticalAttribute
- security-transparent code
- security [.NET Framework], security-transparent code
ms.assetid: 5fd8f46d-3961-46a7-84af-2eb1f48e75cf
ms.openlocfilehash: 97acccdc1dcab11e42d116f4743e1182029e2dd6
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96288195"
---
# <a name="security-transparent-code-level-1"></a>Código transparente en seguridad, nivel 1

[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
 La transparencia ayuda a los desarrolladores a escribir bibliotecas de .NET Framework más seguras que exponen la funcionalidad a código de confianza parcial. La transparencia de nivel 1 se introdujo en .NET Framework versión 2.0 y se usó principalmente solo dentro de Microsoft. A partir de la .NET Framework 4, puede usar la [transparencia de nivel 2](security-transparent-code-level-2.md). Sin embargo, se ha conservado la transparencia de nivel 1 para que pueda identificar código heredado que se debe ejecutar con las reglas de seguridad anteriores.  
  
> [!IMPORTANT]
> Debe especificar la transparencia de nivel 1 solo para la compatibilidad; es decir, especifique el nivel 1 únicamente para el código que se desarrolló con .NET Framework 3.5 o versiones anteriores que usa <xref:System.Security.AllowPartiallyTrustedCallersAttribute> o que no usa el modelo de transparencia. Por ejemplo, use la transparencia de nivel 1 para ensamblados de .NET Framework 2.0 que permiten llamadas de llamadores de confianza parcial (APTCA). Para el código que se desarrolla para el .NET Framework 4, use siempre la transparencia de nivel 2.  
  
 Este tema contiene las siguientes secciones:  
  
- [Modelo de transparencia de nivel 1](#the_level_1_transparency_model)  
  
- [Atributos de transparencia](#transparency_attributes)  
  
- [Ejemplos de transparencia de seguridad](#security_transparency_examples)  
  
<a name="the_level_1_transparency_model"></a>

## <a name="the-level-1-transparency-model"></a>Modelo de transparencia de nivel 1  

 Cuando usa la transparencia de nivel 1, está empleando un modelo de seguridad que separa el código en métodos transparentes en seguridad, críticos para la seguridad y disponibles desde código transparente, y críticos para la seguridad.  
  
 Puede marcar un ensamblado entero, algunas clases de un ensamblado o algunos métodos de una clase como transparentes en seguridad. El código transparente en seguridad no puede elevar privilegios. Esta restricción tiene tres consecuencias:  
  
- El código transparente en seguridad no puede realizar acciones <xref:System.Security.Permissions.SecurityAction.Assert>.  
  
- Cualquier petición de vínculo que se vea satisfecha por código transparente en seguridad se convierte en una demanda completa.  
  
- Cualquier código no seguro (no comprobable) que deba ejecutarse en código transparente en seguridad hace una demanda completa para el permiso de seguridad <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode>.  
  
 Estas reglas se aplican durante la ejecución mediante Common Language Runtime (CLR). El código transparente en seguridad pasa todos los requisitos de seguridad del código al que llama de vuelta a sus llamadores. Las demandas que fluyen a través del código transparente en seguridad no pueden elevar privilegios. Si una aplicación de nivel de confianza bajo llama a código transparente en seguridad y crea una demanda de privilegios altos, la demanda fluirá de vuelta al código de nivel de confianza bajo y producirá un error. El código transparente en seguridad no puede detener la demanda porque no puede realizar acciones Assert. El mismo código transparente en seguridad llamado desde código de plena confianza produce una demanda correcta.  
  
 Crítico para la seguridad es lo contrario de transparente en seguridad. El código crítico para la seguridad se ejecuta con plena confianza y puede realizar todas las operaciones con privilegios. El código crítico para la seguridad y disponible desde código transparente es código con privilegios que se sometió a una auditoría de seguridad exhaustiva para confirmar que no permite que llamadores de confianza parcial usen los recursos para los que no tienen permiso de acceso.  
  
 Debe aplicar la transparencia de forma explícita. La mayoría del código que administra la lógica y la manipulación de datos normalmente se puede marcar como transparente en seguridad, mientras que el menor porcentaje de código que realiza elevaciones de privilegios está marcado como crítico para la seguridad o bien crítico para la seguridad y disponible desde código transparente.  
  
> [!IMPORTANT]
> La transparencia de nivel 1 se limita al ámbito de ensamblado; no se aplica entre ensamblados. La transparencia de nivel 1 se usaba principalmente en Microsoft para realizar auditorías de seguridad. El código transparente en seguridad de otros ensamblados puede acceder a los tipos y miembros críticos para la seguridad dentro de un ensamblado de nivel 1. Es importante que se realicen peticiones de vínculo de plena confianza en todos los tipos y miembros críticos para la seguridad de nivel 1. Los tipos y miembros críticos para la seguridad y disponibles desde código transparente también deben confirmar que los llamadores tengan permisos para los recursos protegidos a los que accede el tipo o miembro.  
  
 Para mantener la compatibilidad con versiones anteriores de .NET Framework, todos los miembros no anotados con atributos de transparencia se consideran críticos para la seguridad y disponibles desde código transparente. Todos los tipos que no están anotados se consideran transparentes. No existen reglas de análisis estático para validar la transparencia. Por lo tanto, puede que necesite depurar errores de transparencia en tiempo de ejecución.  
  
<a name="transparency_attributes"></a>

## <a name="transparency-attributes"></a>Atributos de transparencia  

 En la tabla siguiente se describen los tres atributos que se usan para anotar el código para la transparencia.  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|<xref:System.Security.SecurityTransparentAttribute>|Solo se permite en el nivel de ensamblado. Identifica todos los tipos y miembros del ensamblado como transparentes en seguridad. El ensamblado no puede contener ningún código crítico para la seguridad.|  
|<xref:System.Security.SecurityCriticalAttribute>|Cuando se usa en el nivel de ensamblado sin la propiedad <xref:System.Security.SecurityCriticalAttribute.Scope%2A>, identifica todo el código del ensamblado como transparente en seguridad de forma predeterminada, pero indica que el ensamblado puede contener código crítico para la seguridad.<br /><br /> Cuando se usa en el nivel de clase, identifica la clase o método como crítico para la seguridad, pero no los miembros de la clase. Para que todos los miembros sean críticos para la seguridad, establezca la propiedad <xref:System.Security.SecurityCriticalAttribute.Scope%2A> en <xref:System.Security.SecurityCriticalScope.Everything>.<br /><br /> Cuando se usa en el nivel de miembro, el atributo se aplica solo a ese miembro.<br /><br /> La clase o miembro identificado como crítico para la seguridad puede realizar elevaciones de privilegios. **Importante:**  En la transparencia de nivel 1, los tipos y miembros críticos para la seguridad se tratan como críticos para la seguridad y disponible desde el exterior cuando se les llama desde fuera del ensamblado. Debe proteger los tipos y miembros críticos para la seguridad con una petición de vínculo de plena confianza para evitar la elevación de privilegios no autorizada.|  
|<xref:System.Security.SecuritySafeCriticalAttribute>|Identifica el código crítico para la seguridad al que puede tener acceso el código transparente en seguridad del ensamblado. De lo contrario, el código transparente en seguridad no puede acceder a los miembros críticos para la seguridad privados o internos del mismo ensamblado. Si lo hiciera, podría influir en el código crítico para la seguridad y hacer posibles las elevaciones de privilegios imprevistas. El código crítico para la seguridad y disponible desde código transparente debe someterse a una auditoría de seguridad rigurosa. **Nota:**  Los tipos y miembros críticos para la seguridad y disponible desde acceso seguro deben validar los permisos de los llamadores para determinar si el llamador tiene autoridad para acceder a los recursos protegidos.|  
  
 El atributo <xref:System.Security.SecuritySafeCriticalAttribute> permite que el código transparente en seguridad acceda a los miembros críticos para la seguridad del mismo ensamblado. Considere el código transparente en seguridad y crítico para la seguridad de su ensamblado como si estuviera separado en dos ensamblados. El código transparente en seguridad no sería capaz de ver los miembros privados o internos del código crítico para la seguridad. Además, el código crítico para la seguridad suele auditarse para tener acceso a su interfaz pública. No se espera que un estado privado o interno sea accesible fuera del ensamblado; lo mejor es mantener aislado el estado. El atributo <xref:System.Security.SecuritySafeCriticalAttribute> mantiene el aislamiento del estado entre el código transparente en seguridad y el código crítico para la seguridad, al mismo tiempo que ofrece la capacidad de invalidar el aislamiento si es necesario. El código transparente en seguridad no puede acceder al código crítico para la seguridad privado o interno, a menos que esos miembros se hayan marcado con <xref:System.Security.SecuritySafeCriticalAttribute>. Antes de aplicar <xref:System.Security.SecuritySafeCriticalAttribute>, audite ese miembro como si estuviera expuesto públicamente.  
  
### <a name="assembly-wide-annotation"></a>Anotación de todo el ensamblado  

 En la siguiente tabla se describen los efectos del uso de atributos de seguridad en el nivel de ensamblado.  
  
|Atributo de ensamblado|Estado del ensamblado|  
|------------------------|--------------------|  
|Ningún atributo en un ensamblado de confianza parcial|Todos los tipos y los miembros son transparentes.|  
|Ningún atributo en un ensamblado de plena confianza (en la caché global de ensamblados, o identificado como de plena confianza en `AppDomain`)|Todos los tipos son transparentes y todos los miembros son críticos para la seguridad y disponibles desde código transparente.|  
|`SecurityTransparent`|Todos los tipos y los miembros son transparentes.|  
|`SecurityCritical(SecurityCriticalScope.Everything)`|Todos los tipos y los miembros son críticos para la seguridad.|  
|`SecurityCritical`|El valor predeterminado de todo el código es transparente. Sin embargo, los miembros y tipos individuales pueden tener otros atributos.|  
  
<a name="security_transparency_examples"></a>

## <a name="security-transparency-examples"></a>Ejemplos de transparencia de seguridad  

 Para usar las reglas de transparencia de .NET Framework 2.0 (transparencia de nivel 1), use la siguiente anotación de ensamblado:  
  
```csharp
[assembly: SecurityRules(SecurityRuleSet.Level1)]  
```  
  
 Si desea que un ensamblado entero sea transparente para indicar que no contiene código crítico y que no eleva los privilegios de ninguna manera, puede agregar transparencia explícitamente al ensamblado con el atributo siguiente:  
  
```csharp  
[assembly: SecurityTransparent]  
```  
  
 Si desea mezclar código transparente y crítico en el mismo ensamblado, empiece marcando el ensamblado con el atributo <xref:System.Security.SecurityCriticalAttribute> para indicar que el ensamblado puede contener código crítico, como se indica a continuación:  
  
```csharp  
[assembly: SecurityCritical]  
```  
  
 Si desea realizar acciones críticas para la seguridad, debe marcar explícitamente el código que realizará la acción crítica con otro atributo <xref:System.Security.SecurityCriticalAttribute>, como se muestra en el ejemplo de código siguiente:  
  
```csharp  
[assembly: SecurityCritical]  
public class A  
{  
    [SecurityCritical]  
    private void Critical()  
    {  
        // critical  
    }  
  
    public int SomeProperty  
    {  
        get {/* transparent */ }  
        set {/* transparent */ }  
    }  
}  
public class B  
{
    internal string SomeOtherProperty  
    {  
        get { /* transparent */ }  
        set { /* transparent */ }  
    }  
}  
```  
  
 El código anterior es transparente, excepto el método `Critical`, que se marca explícitamente como crítico para la seguridad. La transparencia es la configuración predeterminada, incluso con el atributo <xref:System.Security.SecurityCriticalAttribute> de nivel de ensamblado.  
  
## <a name="see-also"></a>Vea también

- [Código transparente en seguridad, nivel 2](security-transparent-code-level-2.md)
- [Cambios de seguridad](/previous-versions/dotnet/framework/security/security-changes)
