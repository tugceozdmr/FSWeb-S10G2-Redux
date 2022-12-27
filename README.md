# Redux React Modül Projesi: CRUD Fim

Bugün, redux felsefesini, redux storeunun oluşturulmasını ve bağlantı statetini ve eylemi isteğe bağlı bileşenlere bağlamak için kullanmayı öğrendiniz.

## Giriş

Bu projede, bir film veritabanında arama yapmak için kullanılan oldukça karmaşık bir uygulamayı alıp redux aracılığıyla iki farklı reducer'a bağlacaksınız. Hem mevcut tüm state tanımlarını bağlayacak hem de tüm reducer / redux pairing'lerini sıfırdan oluşturacaksınız.

![Film DB örneği](proje-örneği.gif)

***Görevlerinizi tek tek tamamladığınızdan ve ilerlemeden önce her bir görevi test ettiğinizden emin olun..***

## Talimatlar
### Görev 1: Proje Kurulumu
* [ ] Forklayın.
* [ ] Klonlayın
* [ ] Ana dizine gidin
* [ ] `npm install`
* [ ] `npm start`

### Görev 2: Proje Gereksinimleri
#### Redux Kurulumu
> *DOM ve film reducer sizin için sağlandı, ancak onu redux'a bağlamak size kalmış...*

* [ ] index.js içinde, App'ı redux'a bağlamak için createStore yöntemini ve Provider bileşenini kullanın
.

#### Film reducerını bağlamak
> *Reducers klasörü içinde movieReducers dosyası var. Burada state halihazırda tanımlı ve bazı başlangıç verileri girilmiş. Burdaki state i bileşenimze bağlayalım.*

* [ ] ** movieReducer.js içinde, statein başlangıç değerini initialState olarak atadığımızdan emin olun.** Diğer türlü stateiniz orijinal yapıda olmayacaktır!

* [ ] **MovieList bileşeni, tüm filmlerimizi ekrana yazdırır.** Filmin durum değerini proplarla eşlemek için buradaki connect metodunu kullanın. Statik film değişkenimizi bu proplarla ile değiştirin.

* [ ] **Film bileşeninin çalışması için film listemize erişmesi gerekir.** Filmleri proplarla buraya da gönderin.

* [ ] **Son olarak MovieHeader, başlık metnini görüntülemek için appTitle'ı kullanır..** Bu bileşeni appTitle'a bağlayın ve appTitle'ın uygulamanızda doğru şekilde görüntülendiğini test edin.


#### Sil ve Film Ekle eylemlerini bağlama
> *Görünüşe göre stateToProps'u eşleme konusunda iyi bir fikriniz var! Şimdi bazı eylemleri bağlayalım.*

* [ ] deleteMovie reducer statei ve eylem oluşturucunun zaten mevcut olduğunu unutmayın.

* [ ] **Movie Bileşeni içindeki filmleri silebiliriz.** Connect metodu aracılığıyla deleteMovie eylemini bağlayın.

* [ ] **Movie bileşeninde bir silme işlemini tetiklemesi gereken HTML öğesini bulun.** Geçerli filmin idsinde deleteMovie'yi çağırmak için gerekli event handlerı oluşturun ve bağlayın. State'i ayarladıktan sonra kullanıcıyı push('/movies') komutunu kullanarak yönlendirin..

* [ ] movieReducer.js'ye bir ADD_MOVIE casei ekleyin.
* [ ] Bu yeni casein, payload aracılığıyla iletilen yeni film değerlerine sahip bir state döndürmesini sağlayın
* [ ] movieActions.js'de addMovie için bir eylem oluşturucu oluşturun.
* [ ] Bir filmin eklenmesini tetikleyen bileşeni bulun ve addMovie eylemini bağlayın.
* [ ] addMovie'yi çağırmak için gerekli event handlerı oluşturun ve bağlayın.
* [ ] Yönlendirmeyi tetiklemek için eyleminizi çağırdıktan sonra push('/movies/') öğesini ekleyin.

#### Favoriler reducerı oluşturun
> *Tamam! Artık film reducerı tamamladığınızdan, en sevdiğiniz film işlevselliğini işlemek için sıfırdan bir reducer oluşturma şansınız var. Reducerları birleştirme konusunda çalışacağız.*

* [ ] Favoriler için iş mantığını işlemek için bir reducer dosyası oluşturun. InitialState kurulumunuza aşağıdaki state değerlerini ekleyin:
  -  favorites: film nesnesini içeren bir dizi
  -  displayFavorites: appda favorilerin görüntülendiği bilgisini tutan bir boolean 

* [ ] **Yeni reducerınızı ./reducers/index.js dosyasına import edin.** Başlangıç ​ta, switch deyimine yalnızca bir default case ekleyin.

* [ ] **reducers/index.js'de hem filmleri hem de favori filmleri redux'a bağlamak için CombineReducers metodunu kullanın.**

* [ ] **Film işlevlerinizin artık çalışmadığına dikkat edin. Neden?** Film reducera bağlı bileşenin tekrar çalışmasını sağlamak için gerekli değişiklikleri yapın.

* [ ] Favoriler stateini FavoriteMovieList bileşenine bağlayın ve test edin.

* [ ] DisplayFavorites stateini Movie ve MovieHeader bileşenine bağlayın.

#### Favoriler eylemleri ekleyin
> *Şimdi, uygulamanın geri kalanını kendi başınıza oluşturacaksınız. Bunu yapabilirsiniz!*

1. Aşağıdaki eylemler için reducer caseleri, eylem oluşturucuları ve event handler kodunu ekleyin:
  - toggleFavorites : displayFavorites state değerini true ve false olarak değiştirir. displayFavorites true olduğunda, favori düğmesi Movie sayfasında görünmez.
  
  - addFavorites: Favoriler listesine yeni bir film nesnesi ekler.
  - removeFavorite: Gönderilen bir id ile bir film Nesnesini favoriler listesinden kaldırır.

### Esnek Görevler
- Favoriler görüntülenmiyorsa, kullanıcının bir öğeyi favorilere eklemesine izin vermemek mantıklıdır. Ekleme, favori düğmesinin SADECE displayFavorite true ise görüntülenmesi anlamına gelir.
- Şu anda, aynı filmi birden çok kez favorilerinize ekleyebilirsiniz. Yalnızca listede olmayan filmleri favorilere eklenebilir hale getirmek için AddFavorite eylemini güncelleyin.
- Eğer film ana filmler listesinden silinirse, favorilere ekliyse ordan da silinmelidir, kodunuzu buna göre güncelleyin.
- İçeriklerinizi stilleyin ❤️
