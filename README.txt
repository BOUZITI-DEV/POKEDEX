explication de la réalisation du projet :

.ajout des dépendances necessaires dans le fichier build.gradle:
	cardview	: bibliothèque qui contient un composant UI qui va nous permettre d'afficher les données des pokemon sous forme de cartes.
	recylceview : bibliothèque qui contient un composant UI qui va nous permettre d'afficher une grande quantité de données(la liste des pokemons).
	retrofit2 	: bibliothèque pour utiliser l'API 
	glide       : bibliothèque pour charger les images des pokemons
	
	
.création du drawable pokemon_bg.xml qui va permettre de changer la couleur de l'arrière plan de l'activité principale

.création du layout item_pokemon qui contiendra les propriétés graphiques du contenaire de chaque pokemon

.le fichier activity_main.xml contiendra une liste(la liste des pokemon) en utilisant un TAG recycleview

.création de la classe Pokemon

.création de la classe PokemonRequester qui contient une liste de pokemon (ces pokemon seront fourni ensuite par l'API)

.création de l'interface PokeapiService qui va permettre l'acces à l'API PokeApi en utilisant la librairie Retrofit

.la classe MainActivity hérite de la classe AppCompactActivity
	la méthode onCreate() permet d'initialiser le RecycleView, GridLayoutManager et un OnScrollListner
	l'objet retrofit est initalisé avec l'URL du PokeAPI
	la méthode getInformation() permet de récupérer les premiers 20 pokemon en envoyant une requête HTTP à PokeApi pour obtenir un objet PokemonRequester qui contiendra la liste des pokemons
	la methode enqueue() permet de rendre la requête asynchrone pour ne pas ralentir l'application
	la méthode onFailure est appelée en cas d'erreurs
	OnScrollListner est utilisé pour detecter si l'utilisateur déroule vers la fin de la liste, si c'est la cas, la methode getInformation est encore une fois appelée pour charger plus de pokemon
	la varible fitToCharge est utilisé pour ne pas faire de requêtes lorqu'une autre requête est dejà en cours.(une seule requête à la fois)
	
	