    1. Selects the names of all products that are not on sale.

    SELECT name FROM products WHERE on_sale='f';
    Teddy Bear
    Cat Ears
    Card Against Humanity
    Set of 12 Mason Jars

    2. Selects the names of all products that cost less than £20.

    SELECT name FROM products WHERE price<20;
    Teddy Bear
    The Ruby Programming Language
    Silicon Valley Monopoly
    Set of 12 Mason Jars

    3. Selects the name and price of the most expensive product.

    SELECT name, price FROM products ORDER BY price DESC LIMIT 1;
    Cat Ears|99.99

    4. Selects the name and price of the second most expensive product.

    SELECT name, price FROM products ORDER BY price DESC LIMIT 1 OFFSET 2;
    Lonely Pillow|78.82

    5. Selects the name and price of the least expensive product.

    SELECT name, price FROM products ORDER BY price ASC LIMIT 1;
    Set of 12 Mason Jars|6.22

    6. Selects the names and prices of all products, ordered by price in descending order.

    SELECT name, price FROM products ORDER BY price DESC;
    Cat Ears|99.99
    Brown Leather Boots|82.0
    Lonely Pillow|78.82
    Card Against Humanity|25.0
    Hoodie|25.0
    Set of silverware|22.99
    The Ruby Programming Language|19.99
    Teddy Bear|17.99
    Silicon Valley Monopoly|10.99
    Set of 12 Mason Jars|6.22

    7. Selects the average price of all products.

    SELECT avg(price) FROM products;
    38.899

    8. Selects the sum of the price of all products.

    SELECT sum(price) FROM products;
    388.99

    9. Selects the sum of the price of all products whose prices is less than £20.

    SELECT total(price) FROM products WHERE price < 20;
    55.19

    10. Selects the id of the user with your name.

    SELECT id FROM users where name = 'Erika Jonikaite';

    11. Selects the names of all users whose names start with the letter "J".

    SELECT name FROM users WHERE substr(name,1,1) in ('J');
    Jon Rogers
    James Gotsell

    12. Selects the number of users whose first names are "Spencer".

    SELECT name FROM users WHERE substr(name,1,7) in ('Spencer');
    Spencer Meyer

    13. Selects the number of users who want a "Teddy Bear".

    SELECT id FROM products WHERE name ="Teddy Bear";
    1
    SELECT count(user_id) FROM wishlists WHERE product_id = 1;
    6

    14. Selects the count of items on the wishlish of the user with your name.

    SELECT count(*) FROM wishlists WHERE user_id in (select id from users where name ="Erica Porter"); 
    4

    15. Selects the count and name of all products on the wishlist, ordered by count in descending order.




    16. Selects the count and name of all products that are not on sale on the wishlist, ordered by count in descending order.





    17. Inserts a user with the name "Jonathan Anderson" into the users table. Ensure the created_at column is set to the current time.

    INSERT INTO users (created_at, name) values (CURRENT_TIMESTAMP, "Jonathan Anderson");
    15|2015-05-25 22:18:12|Jonathan Anderson

    18. Selects the id of the user with the name "Jonathan Anderson"?

    SELECT id FROM users WHERE name = "Jonathan Anderson";
    15

    19. Inserts a wishlist entry for the user with the name "Jonathan Anderson" for the product "The Ruby Programming Language".

    INSERT INTO wishlists (user_id, product_id) VALUES ((SELECT id FROM users WHERE name ="Jonathan Anderson"), (SELECT id FROM products WHERE name ="The Ruby Programming Language"));

    20. Updates the name of the "Jonathan Anderson" user to be "Jon Anderson".

    UPDATE users SET name="Jon Anderson" WHERE name="Jonathan Anderson";

    21. Deletes the user with the name "Jon Anderson".

    DELETE FROM users WHERE name="Jon Anderson";

    22. Deletes the wishlist item for the user you just deleted.


