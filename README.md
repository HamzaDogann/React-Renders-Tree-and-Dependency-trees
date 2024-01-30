# React Renders ve Dependency Trees

Bu README dosyası, React uygulamalarında "renders" ve "dependency trees" konularını anlatır. Aşağıda bu konseptlerin ne olduğunu ve nasıl kullanıldığını anlamak için bir açıklama ve örnek bulacaksınız.

## Renders Nedir?

React uygulamalarında "render", bir bileşenin bir JSX elementini ekrana çizmesidir. Bu işlem, bir bileşenin durumu veya props'u değiştiğinde gerçekleşir. React, sadece değişen kısımları güncellemek için sanal DOM kullanır, böylece sayfanın tamamını yeniden yüklemek zorunda kalmaz.

## Dependency Trees Nedir?

Dependency trees (bağımlılık ağaçları), bir bileşenin render işleminin gerçekleşmesi için gereken bağımlılıkların bir ağacını temsil eder. Bu bağımlılıklar, bileşenin durumu, props'ları veya bağlamı gibi şeyler olabilir. Bir bileşenin bağımlılık ağacı, o bileşenin render işlemi sırasında hangi parçaların güncelleneceğini belirler.

## Örnek: UserList Bileşeni

Aşağıda, basit bir `UserList` bileşeni ve onun bağımlılık ağacıyla ilgili bir örnek bulunmaktadır:

```jsx
import React from 'react';

class UserList extends React.Component {
  render() {
    const { users } = this.props;
    return (
      <div>
        <h2>Users</h2>
        <ul>
          {users.map(user => (
            <li key={user.id}>{user.name}</li>
          ))}
        </ul>
      </div>
    );
  }
}

export default UserList;
```

Yukarıdaki `UserList` bileşeni, `users` adında bir prop alır ve her bir kullanıcı için bir `<li>` elementi oluşturur.

Bağımlılık ağacı şu şekildedir:
- `UserList` bileşeni `users` prop'una bağımlıdır. Yani, `users` prop'u değiştiğinde, `UserList` bileşeni yeniden render edilir.

Bu örnek, bir bileşenin nasıl render edildiğini ve bağımlılıklarının nasıl belirlendiğini anlamak için iyi bir örnek sağlar.

## Katkıda Bulunma

Bu README dosyası açık kaynaklıdır. Eğer bir hata bulursanız veya katkıda bulunmak isterseniz, lütfen GitHub'da bir pull isteği açın!
