# Ιστορικό <a href="HISTORY.md"> <img width="20px" src="https://iris-go.com/images/flag-unitedkingdom.svg?v=10" /></a> <a href="HISTORY_ZH.md"> <img width="20px" src="https://iris-go.com/images/flag-china.svg?v=10" /></a>

### Ψάχνετε για δωρεάν υποστήριξη σε πραγματικό χρόνο;

    https://github.com/kataras/iris/issues
    https://chat.iris-go.com

### Ψάχνετε για προηγούμενες εκδόσεις;

    https://github.com/kataras/iris/releases

### Πρέπει να αναβαθμίσω το Iris μου;

Οι προγραμματιστές δεν αναγκάζονται να αναβαθμίσουν αν δεν το χρειάζονται πραγματικά. Αναβαθμίστε όποτε αισθάνεστε έτοιμοι.

> Το Iris εκμεταλλεύεται τη λεγόμενη λειτουργία [vendor directory](https://docs.google.com/document/d/1Bz5-UB7g2uPBdOx-rw5t9MxJwkfpx90cqG9AFL0JAYo). Παίρνετε πλήρως αναπαραγωγίσιμα builds, καθώς αυτή η μέθοδος προστατεύει από τις upstream μετονομασίες και διαγραφές.

**Πώς να αναβαθμίσετε**: Ανοίξτε την γραμμή εντολών σας και εκτελέστε αυτήν την εντολή: `go get -u github.com/kataras/iris`  ή αφήστε το αυτόματο updater να το κάνει αυτό για σας.

# Mo, 01 Jenuary 2018 | v10.0.0

Πρέπει να ευχαριστήσουμε την [Κυρία Diana](https://www.instagram.com/merry.dii/) για το νέο μας [λογότυπο](https://iris-go.com/images/icon.svg)!

Μπορείτε να [επικοινωνήσετε](mailto:Kovalenkodiana8@gmail.com) μαζί της για οποιεσδήποτε σχετικές με το σχεδιασμό εργασίες ή να της στείλειτε ένα άμεσο μήνυμα μέσω [instagram](https://www.instagram.com/merry.dii/).

<p align="center">
<img width="145px" src="https://iris-go.com/images/icon.svg?v=a" />
</p>

Σε αυτή την έκδοση έχουμε πολλές εσωτερικές βελτιώσεις αλλά μόνο δύο μεγάλες αλλαγές και ένα μεγάλο χαρακτηριστικό, που ονομάζεται **hero**.

> Η νέα έκδοση προσθέτει 75 καινούρια commits, το PR βρίσκεται [εδώ](https://github.com/kataras/iris/pull/849). Παρακαλώ διαβάστε τις εσωτερικές αλλαγές αν σχεδιάζετε ένα web framework που βασίζεται στο Iris. Γιατί η έκδοση 9 παραλείφθηκε; Έτσι.

## Hero

Το νέο πακέτο [hero](hero) περιέχει χαρακτηριστικά για σύνδεση(binding) οποιουδήποτε αντικειμένου ή function το οποίο τα `handlers` μπορεί να χρησημοποιούν, αυτά λεγόνται εξαρτήσεις(dependencies). Τα Hero funcs μπορούν επίσης να επιστρέψουν οποιαδήποτε τιμή, οποιουδήποτε τύπου, αυτές οι τιμές αποστέλλονται στον πελάτη(client).

> Μπορεί να είχατε ξαναδει "εξαρτήσεις" και "δέσιμο" πριν αλλά ποτέ με υποστήριξη από τον επεξεργαστή κώδικα (code editor), με το Iris πέρνεις πραγματικά ασφαλή "δεσίματα"(bindings) χάρη στο νέο `hero` πακέτο. Αυτή η όλη εκτέλεση(implementation) είναι επίσης η ποιο γρήγορη που έχει επιτευχθεί εως τώρα, η επίδοση είναι πολύ κοντά στα απλά "handlers" και αυτό γιατί το Iris υπολογίζει τα πάντα πριν καν ο server τρέξει!

Παρακάτω θα δείτε μερικά στιγμιότυπα που ετοιμάσαμε για εσάς, ώστε να γίνουν πιο κατανοητά τα παραπάνω:

### 1. Παράμετροι διαδρομής - Ενσωματωμένες Εξαρτήσεις (Built'n Dependencies)

![](https://github.com/kataras/explore/raw/master/iris/hero/hero-1-monokai.png)

### 2. Υπηρεσίες - Στατικές Eξαρτήσεις (Static Dependencies)

![](https://github.com/kataras/explore/raw/master/iris/hero/hero-2-monokai.png)

### 3. Ανά Αίτηση - Δυναμικές Eξαρτήσεις (Dynamic Dependencies)

![](https://github.com/kataras/explore/raw/master/iris/hero/hero-3-monokai.png)

Είναι πραγματικά πολύ εύκολο να καταλάβεις πως δουλεύουν τα `hero funcs` και όταν αρχίσεις να τα χρησιμοποιείς **δεν γυρίζεις ποτέ πίσω**.

Παραδείγματα:

- [Βασικό](_examples/hero/basic/main.go)
- [Επισκόπηση](_examples/hero/overview)

## MVC

Πρέπει να καταλάβεις πως δουλεύει το `hero` πακετό ώστε να να δουλέψεις με το `mvc`, γιατί το `mvc` πακέτο βασίζετε στο `hero` για τις μεθόδους του controller σου, οι ίδιοι κανόνες εφαρμόζονται και εκεί.

Παραδείγματα:

**Αν χρησημοποιούσατε το MVC πριν, διαβάστε προσεχτικά: Το MVC ΠΕΡΙΕΧΕΙ ΟΡΙΣΜΕΝΕΣ ΑΛΛΑΓΕΣ, ΜΠΟΡΕΙΤΕ ΝΑ ΚΑΝΕΤΕ ΠΕΡΙΣΣΟΤΕΡΑ ΑΠΟ'ΤΙ ΠΡΙΝ**

**ΠΑΡΑΚΑΛΩ ΔΙΑΒΑΣΤΕ ΤΑ ΠΑΡΑΔΕΙΓΜΑΤΑ ΠΡΟΣΕΧΤΙΚΑ, ΓΙΑ ΕΣΑΣ ΦΤΙΑΧΤΗΚΑΝ**

Τα παλιά παραδείγματα είναι επίσης εδώ ώστε να μπορείτε να τα συγκρίνετε με τα καινούρια.

| ΤΩΡΑ | ΠΡΙΝ |
| -----------|-------------|
| [Hello world](_examples/mvc/hello-world/main.go) | [ΠΑΛΙΟ Hello world](https://github.com/kataras/iris/blob/v8/_examples/mvc/hello-world/main.go) |
| [Session Controller](_examples/mvc/session-controller/main.go) | [ΠΑΛΙΟ Session Controller](https://github.com/kataras/iris/blob/v8/_examples/mvc/session-controller/main.go) |
| [Overview - Plus Repository and Service layers](_examples/mvc/overview) | [ΠΑΛΙΟ Overview - Plus Repository and Service layers](https://github.com/kataras/iris/tree/v8/_examples/mvc/overview) |
| [Login showcase - Plus Repository and Service layers](_examples/mvc/login) | [ΠΑΛΙΟ Login showcase - Plus Repository and Service layers](https://github.com/kataras/iris/tree/v8/_examples/mvc/login) |
| [Singleton](_examples/mvc/singleton) |  **NEO** |
| [Websocket Controller](_examples/mvc/websocket) |  **NEO** |
| [Vue.js Todo MVC](_examples/tutorial/vuejs-todo-mvc) |  **NEO** |

## context#PostMaxMemory

Αφαίρεση της παλιάς στατικής μεταβλητής `context.DefaultMaxMemory` και αντικατάσταση με ρύθμιση στο configuration `WithPostMaxMemory`.

```go
// WithPostMaxMemory sets the maximum post data size
// that a client can send to the server, this differs
// from the overral request body size which can be modified
// by the `context#SetMaxRequestBodySize` or `iris#LimitRequestBodySize`.
//
// Defaults to 32MB or 32 << 20 if you prefer.
func WithPostMaxMemory(limit int64) Configurator
```

Αν χρησημοποιούσατε την παλιά στατική μεταβλητή θα χρειαστεί να κάνετε μια αλλαγή σε εκείνη τη γραμμή του κώδικα.

```go
import "github.com/kataras/iris"

func main() {
    app := iris.New()
    // [...]

    app.Run(iris.Addr(":8080"), iris.WithPostMaxMemory(10 << 20))
}
```

## context#UploadFormFiles

Νέα μέθοδος για ανέβασμα πολλαπλών αρχείων από τον client, πρέπει να χρησημοποιείται για απλές και συνηθισμένες καταστάσεις, ένα helper είναι μόνο.

```go
// UploadFormFiles uploads any received file(s) from the client
// to the system physical location "destDirectory".
//
// The second optional argument "before" gives caller the chance to
// modify the *miltipart.FileHeader before saving to the disk,
// it can be used to change a file's name based on the current request,
// all FileHeader's options can be changed. You can ignore it if
// you don't need to use this capability before saving a file to the disk.
//
// Note that it doesn't check if request body streamed.
//
// Returns the copied length as int64 and
// a not nil error if at least one new file
// can't be created due to the operating system's permissions or
// http.ErrMissingFile if no file received.
//
// If you want to receive & accept files and manage them manually you can use the `context#FormFile`
// instead and create a copy function that suits your needs, the below is for generic usage.
//
// The default form's memory maximum size is 32MB, it can be changed by the
//  `iris#WithPostMaxMemory` configurator at main configuration passed on `app.Run`'s second argument.
//
// See `FormFile` to a more controlled to receive a file.
func (ctx *context) UploadFormFiles(
        destDirectory string,
        before ...func(string, string),
    ) (int64, error)
```

Το παράδειγμα μπορεί να βρεθεί [εδώ](_examples/http_request/upload-files/main.go).

## context#View

Απλά μια μικρή προσθήκη μια δεύτερης προαιρετικής variadic παράμετρου στη `context#View` μέθοδο για να δέχεται μια μονή τιμή για template binding.
Όταν απλά θέλετε να εμφάνισετε ένα struct value και όχι ζεύγη από κλειδί-τιμή, παλιότερα για να το κάνετε αυτό έπρεπε να δηλώσετε κενό string στη 1η παράμετρο στη `context#ViewData` μέθοδο, το οποίο είναι μια χαρά ειδικά αν δηλώνατε αυτά τα δεδομένα σε προηγούμενο handler της αλυσίδας.

```go
func(ctx iris.Context) {
    ctx.ViewData("", myItem{Name: "iris" })
    ctx.View("item.html")
}
```

Το ίδιο όπως:

```go
func(ctx iris.Context) {
    ctx.View("item.html", myItem{Name: "iris" })
}
```

```html
Item's name: {{.Name}}
```

## context#YAML

Προσθήκη νέας μεθόδου, `context#YAML`, εμφανίζει δομημένο yaml κείμενο από struct value.

```go
// YAML marshals the "v" using the yaml marshaler and renders its result to the client.
func YAML(v interface{}) (int, error)
```

## Session#GetString

Η μέθοδος `sessions/session#GetString` μπορεί πλέον να επιστρέψει τιμή ακόμα και απο τιμή που αποθηκεύτηκαι σαν αριθμός (integer), όπως ακριβώς κάνουν ήδη τα: memstore, η προσωρινή μνήμη του context, οι δυναμικές μεταβλητές του path routing και οι παράμετροι του url query.