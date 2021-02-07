---
description: 'Más información sobre: procedimientos recomendados de confianza parcial'
title: Procedimientos recomendados de confianza parcial
ms.date: 03/30/2017
ms.assetid: 0d052bc0-5b98-4c50-8bb5-270cc8a8b145
ms.openlocfilehash: abdc0fbbb84581b302bca8d514a5f8f5cc2703e6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99733559"
---
# <a name="partial-trust-best-practices"></a>Procedimientos recomendados de confianza parcial

En este tema se describen los procedimientos recomendados para ejecutar Windows Communication Foundation (WCF) en un entorno de confianza parcial.

## <a name="serialization"></a>Serialización

Aplique los siguientes procedimientos al utilizar <xref:System.Runtime.Serialization.DataContractSerializer> en una aplicación de confianza parcial.

- Se ha de marcar a todos los tipos serializables mediante el atributo `[DataContract]`. Las siguientes técnicas no se admiten en un entorno de confianza parcial:

- Marcado de clases que se van a serializar con el <xref:System.SerializableAttribute>.

- Implementación de la interfaz <xref:System.Runtime.Serialization.ISerializable> para permitir que una clase controle su proceso de serialización.

### <a name="using-datacontractserializer"></a>Uso de DataContractSerializer

- Todos los tipos marcados con el atributo `[DataContract]` deben ser públicos. Los tipos no públicos no se pueden serializar en un entorno de confianza parcial.

- Todos los miembros de `[DataContract]` de un tipo de `[DataContract]` serializable deben ser públicos. Un tipo con un `[DataMember]` no público no se puede serializar en un entorno de confianza parcial.

- Los métodos que administran eventos de serialización (como `OnSerializing`, `OnSerialized`, `OnDeserializing`y `OnDeserialized`) se deben declarar como públicos. Sin embargo, se admiten las implementaciones explícitas e implícitas de <xref:System.Runtime.Serialization.IDeserializationCallback.OnDeserialization%28System.Object%29>.

- Los tipos `[DataContract]` implementados en ensamblados marcados con el <xref:System.Security.AllowPartiallyTrustedCallersAttribute> no deben realizar acciones relacionadas con la seguridad en el constructor de tipos, puesto que el <xref:System.Runtime.Serialization.DataContractSerializer> no llama durante la deserialización al constructor del objeto del que se ha creado recientemente una instancia. Particularmente, se han de evitar las siguientes técnicas de seguridad comunes en los tipos de `[DataContract]`:

- Intentar restringir el acceso de confianza parcial haciendo interno o privado el constructor del tipo.

- Restringir el acceso al tipo agregando una `[LinkDemand]` al constructor del tipo.

- Suponer que, como se ha creado una instancia del objeto correctamente, todas las comprobaciones de validación requeridas por el constructor se han superado con éxito.

### <a name="using-ixmlserializable"></a>Utilizar IXmlSerializable

Los siguientes procedimientos recomendados se aplican a tipos que implementan <xref:System.Xml.Serialization.IXmlSerializable> y se serializan mediante <xref:System.Runtime.Serialization.DataContractSerializer>.

- Las implementaciones del método estático <xref:System.Xml.Serialization.IXmlSerializable.GetSchema%2A> deben ser `public`.

- Los métodos de instancia que implementan la interfaz <xref:System.Xml.Serialization.IXmlSerializable> deben ser `public`.

## <a name="using-wcf-from-fully-trusted-platform-code-that-allows-calls-from-partially-trusted-callers"></a>Utilizar WCF a partir de código de la plataforma de plena confianza que permite llamadas desde llamadores de confianza parcial

El modelo de seguridad de confianza parcial de WCF supone que cualquier llamador de una propiedad o método público de WCF se está ejecutando en el contexto de seguridad de acceso del código (CAS) de la aplicación de hospedaje. WCF también supone que solo existe un contexto de seguridad de la aplicación para cada <xref:System.AppDomain> , y que este contexto se establece en el momento de la <xref:System.AppDomain> creación por parte de un host de confianza (por ejemplo, mediante una llamada a <xref:System.AppDomain.CreateDomain%2A> o mediante el administrador de aplicaciones de ASP.net).

Este modelo de seguridad se aplica a las aplicaciones escritas por usuarios que no pueden validar permisos CAS adicionales, como, por ejemplo, el código de usuario que se ejecuta en una aplicación ASP.NET de nivel de confianza medio. Sin embargo, el código de plataforma de plena confianza (por ejemplo, un ensamblado de terceros que se instala en la caché global de ensamblados y acepta llamadas del código de confianza parcial) debe tener cuidado explícito al llamar a WCF en nombre de una aplicación de confianza parcial para evitar la introducción de vulnerabilidades de seguridad de nivel de aplicación.

El código de plena confianza debe evitar modificar el conjunto de permisos CAS del subproceso actual (llamando a <xref:System.Security.PermissionSet.Assert%2A> , <xref:System.Security.PermissionSet.PermitOnly%2A> o <xref:System.Security.PermissionSet.Deny%2A> ) antes de llamar a las API de WCF en nombre del código de confianza parcial. Validar, denegar o crear un contexto de permiso para subprocesos que sea independiente del contexto de seguridad de aplicaciones puede provocar un comportamiento inesperado. En función de la aplicación, este comportamiento puede producir vulnerabilidades de seguridad en aplicaciones.

El código que llama a WCF mediante un contexto de permiso específico del subproceso debe estar preparado para controlar las siguientes situaciones que pueden surgir:

- El contexto de seguridad específico para subprocesos no se puede mantener durante toda la operación, lo que produce excepciones de seguridad potenciales.

- El código de WCF interno, así como las devoluciones de llamada proporcionadas por el usuario, se pueden ejecutar en un contexto de seguridad diferente que el en el que se inició originalmente la llamada. Entre estos contextos se incluyen:

  - El contexto del permiso de aplicación.

  - Cualquier contexto de permiso específico del subproceso creado previamente por otros subprocesos de usuario utilizados para llamar a WCF durante la duración de la ejecución actual <xref:System.AppDomain> .

WCF garantiza que el código de confianza parcial no puede obtener permisos de plena confianza a menos que los permisos sean impuestas por un componente de plena confianza antes de llamar a las API públicas de WCF. Sin embargo, no garantiza que los efectos de validar la plena confianza se aíslen a un determinado subproceso, operación o acción del usuario.

A modo de procedimiento recomendado, evite crear un contexto de permiso para subprocesos llamando al método <xref:System.Security.PermissionSet.Assert%2A>, <xref:System.Security.PermissionSet.PermitOnly%2A> o <xref:System.Security.PermissionSet.Deny%2A>. En su lugar, conceda o deniegue el privilegio a la propia aplicación, para que no se requiera <xref:System.Security.PermissionSet.Assert%2A>, <xref:System.Security.PermissionSet.Deny%2A> o <xref:System.Security.PermissionSet.PermitOnly%2A>.

## <a name="see-also"></a>Vea también

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.Xml.Serialization.IXmlSerializable>
