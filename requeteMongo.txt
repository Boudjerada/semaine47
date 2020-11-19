/*Base Jartitou où les tables produits et catégories sont fusionnés */

/* INSERTION*/

 db.produits.insert({
    "_id": 7,
    "pro_cat_nom": "Barbecues",
    "pro_cat_parent_nom": "Mobilier de jardin",
    "pro_ref": "barb001",
    "pro_libelle": "Aramis",
    "pro_description": "Lorem ipsum dolor sit amet, consectetur adipiscing elit. In porttitor sit amet ipsum sit amet dapibus. Cras suscipit neque ac magna sagittis lobortis. Duis venenatis enim ac nisl luctus, a scelerisque velit porttitor. Integer nec massa quis urna mollis consectetur et et nisl. Nullam eget nunc vitae nisl convallis faucibus. Vestibulum dapibus, metus nec molestie lobortis, nunc sem mollis tortor, et auctor dolor nunc at nisi. Pellentesque sit amet turpis nisi.",
    "pro_prix": 110,
    "pro_stock": 2,
    "pro_couleur": "Brun",
    "pro_photo": "jpg",
    "pro_d_ajout": "2018-04-18"
}

 db.produits.insert({
    "_id": 8,
    "pro_cat_nom": "Barbecues",
    "pro_cat_parent_nom": "Mobilier de jardin",
    "pro_ref": "barb002",
    "pro_libelle": "Athos",
    "pro_description": "Curabitur pellentesque posuere luctus. Sed et risus vel quam pharetra pretium non quis odio. Praesent varius risus vel orci ultrices tincidunt.",
    "pro_prix": 249.99,
    "pro_stock": 0,
    "pro_couleur": "Noir",
    "pro_photo": "jpg",
    "pro_d_ajout": "2016-06-14"
}

db.produits.insert({
    "_id": 11,
    "pro_cat_nom": "Barbecues",
    "pro_cat_parent_nom": "Mobilier de jardin",
    "pro_ref": "barb003",
    "pro_libelle": "Clatronics",
    "pro_description": "Fusce rutrum odio sem, quis finibus nisl finibus a. Praesent dictum ex in lectus porta, vitae varius lacus eleifend. Sed sed lacinia mi, sed egestas odio. Integer a congue lectus.",
    "pro_prix": 135.9,
    "pro_stock": 10,
    "pro_couleur": "Chromer",
    "pro_photo": "jpg",
    "pro_d_ajout": "2017-10-18"
}

db.produits.insert({
    "_id": 12,
    "pro_cat_nom": "Barbecues",
    "pro_cat_parent_nom": "Mobilier de jardin",
    "pro_ref": "barb004",
    "pro_libelle": "Camping",
    "pro_description": "Phasellus auctor mattis justo, in semper urna congue eget. Nunc sit amet nunc sed dui fringilla scelerisque a eget sem. Aenean cursus eros vehicula arcu blandit, sit amet faucibus leo finibus. Duis pharetra felis eget viverra tempor. Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas",
    "pro_prix": 88,
    "pro_stock": 5,
    "pro_couleur": "Noir",
    "pro_photo": "jpg",
    "pro_d_ajout": "2018-08-20",
    "pro_bloque": 1
}

db.produits.insert({
    "_id": 13,
    "pro_cat_nom": "Brouettes",
    "pro_cat_parent_nom": "Outillage manuel",
    "pro_ref": "brou001",
    "pro_libelle": "Green",
    "pro_description": "Fusce interdum ex justo, vel imperdiet erat volutpat non. Donec et maximus lacus.",
    "pro_prix": 49,
    "pro_stock": 25,
    "pro_couleur": "Verte",
    "pro_photo": "jpg",
    "pro_d_ajout": "2018-08-01"
}

/*SELECTION*/

db.produits.find(
   {"pro_cat_nom":"Barbecues","pro_bloque":1})

/*Affichage juste du libelle*/

db.produits.find(
   {"pro_cat_nom":"Barbecues","pro_bloque":1},{pro_libelle:1})

/*Modification */

 db.produits.update( { "pro_ref": "barb004" }, { $set: { "pro_prix": 100 } } )

 /*Plusieurs documents modification*/

 db.produits.update( { "pro_stock": { $gt: 3 } }, { $set: { "pro_prix": 200 } }, { multi: 1 } )

/*Suppression*/
db.produits.deleteOne( { "pro_ref": "barb003" })