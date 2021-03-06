---
title: "EDM (модель данных с использованием сущностей)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2dda3d5b-4582-4ba0-a91d-fcd7a1498137
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: e1a1bdeffcc85383d241c277240187ede41401cd
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="entity-data-model"></a>EDM (модель данных с использованием сущностей)
Модель EDM - это набор основных понятий, которые описывают структуру данных независимо от формы хранения. Модель EDM заимствует свойства модели «сущность-связь», описанной Питером Ченом в 1976 г., более того, она строится на модели «сущность-связь» и расширяет возможности ее традиционного использования.  
  
 Модель EDM решает проблемы, возникающие из необходимости хранить данные в различных формах. Например, предположим, есть фирма, которая хранит данные в реляционных базах данных, текстовых файлах, файлах XML, электронных таблицах и отчетах. Это является значительным препятствием для моделирования данных, проектирования приложений и доступа к данным. Во время проектирования приложения, ориентированного на работу с данными, сложность заключается в написании эффективного и поддерживаемого кода без ущерба для эффективности доступа к данным, хранения и масштабируемости. Если данные имеют реляционную структуру, доступ к данным, хранение и масштабируемость будут весьма эффективными, однако написание эффективного и поддерживаемого кода становится более сложным. Если данные имеют структуру объекта, компромиссы приобретают обратный характер: написание эффективного и поддерживаемого кода наносит ущерб эффективности доступа к данным, хранения и масштабируемости. Даже если для этих компромиссов будут найдены правильные решения, при перемещении данных из одной формы в другую возникают новые трудности. Модель EDM решает эти трудности путем описания структуры данных на основе сущностей и связей, которые являются независимыми от схем хранения. В результате форма хранения данных уже не имеет отношения к проектированию приложений и разработке. Поскольку сущности и связи описывают структуру данных так, как она используется в приложении (а не ее форму хранения), они могут эволюционировать по мере эволюции приложения.  
  
 `conceptual model` - это специфическое представление структуры данных в виде сущностей и связей, которое обычно определяется на доменном языке DSL, реализующем основные понятия модели EDM. [Язык определения концептуальной схемы (CSDL)](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md) приведен пример такого доменного языка. Сущности и связи, описанные в концептуальной модели, можно представить в виде абстракций объектов и ассоциаций в приложении. Это позволяет разработчикам сфокусировать внимание на концептуальной модели, не думая о схеме хранения, и писать эффективный и поддерживаемый код. Одновременно разработчики схем хранения могут сфокусировать внимание на эффективности доступа к данным, хранения и масштабируемости.  
  
## <a name="in-this-section"></a>Содержание  
 В подразделах этого раздела описываются основные понятия модели EDM. Любой специфический язык домена (DSL), реализующий модель EDM, должен включать основные понятия, описанные в данном разделе. Обратите внимание, что [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) использует язык CSDL для определения концептуальных моделей. Дополнительные сведения см. в разделе [спецификация языка CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md).  
  
 [Основные понятия модели EDM](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
  
 [Модель EDM. Пространство имен](../../../../docs/framework/data/adonet/entity-data-model-namespaces.md)  
  
 [Модель EDM. Примитивные типы данных](../../../../docs/framework/data/adonet/entity-data-model-primitive-data-types.md)  
  
 [Модель EDM. Наследование](../../../../docs/framework/data/adonet/entity-data-model-inheritance.md)  
  
 [конечная точка ассоциации](../../../../docs/framework/data/adonet/association-end.md)  
  
 [кратность конечной точки ассоциации](../../../../docs/framework/data/adonet/association-end-multiplicity.md)  
  
 [набор ассоциаций](../../../../docs/framework/data/adonet/association-set.md)  
  
 [конечная точка набора ассоциаций](../../../../docs/framework/data/adonet/association-set-end.md)  
  
 [тип ассоциации](../../../../docs/framework/data/adonet/association-type.md)  
  
 [сложный тип](../../../../docs/framework/data/adonet/complex-type.md)  
  
 [контейнер сущности](../../../../docs/framework/data/adonet/entity-container.md)  
  
 [ключ сущности](../../../../docs/framework/data/adonet/entity-key.md)  
  
 [набор сущности](../../../../docs/framework/data/adonet/entity-set.md)  
  
 [тип сущности](../../../../docs/framework/data/adonet/entity-type.md)  
  
 [facet](../../../../docs/framework/data/adonet/facet.md)  
  
 [свойство внешнего ключа](../../../../docs/framework/data/adonet/foreign-key-property.md)  
  
 [объявляемая моделью функция](../../../../docs/framework/data/adonet/model-declared-function.md)  
  
 [определяемая моделью функция](../../../../docs/framework/data/adonet/model-defined-function.md)  
  
 [свойство навигации](../../../../docs/framework/data/adonet/navigation-property.md)  
  
 [свойство](../../../../docs/framework/data/adonet/property.md)  
  
 [ограничение ссылочной целостности](../../../../docs/framework/data/adonet/referential-integrity-constraint.md)  
  
## <a name="see-also"></a>См. также  
 [Средства работы с моделью EDM ADO.NET](http://msdn.microsoft.com/library/91076853-0881-421b-837a-f582f36be527)  
 [Общие сведения о файлах .edmx](http://msdn.microsoft.com/library/f4c8e7ce-1db6-417e-9759-15f8b55155d4)  
 [Спецификация CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)
