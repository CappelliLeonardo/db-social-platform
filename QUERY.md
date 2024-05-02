<!-- 1. Seleziona tutti gli utenti e calcolane l'età (25)

SELECT * ,TIMESTAMPDIFF(YEAR, birthdate, CURDATE()) AS age FROM users;


2. Seleziona tutti i post senza Like (13)

SELECT * FROM posts WHERE id NOT IN (SELECT post_id FROM likes);


3. Conta il numero di like per ogni post (165)

SELECT p.id AS post_id, p.title AS post_title, (SELECT COUNT(*) FROM likes WHERE post_id = p.id) AS num_likes FROM posts p;

4. Ordina gli utenti per il numero di media caricati (25)

SELECT u.username, u.email, COUNT(p.id) AS num_posts FROM users u LEFT JOIN posts p ON u.id = p.user_id GROUP BY u.id ORDER BY num_posts DESC;


5. Ordina gli utenti per totale di likes ricevuti nei loro posts (25)

SELECT u.username, u.email, COUNT(l.post_id) AS total_likes FROM users u LEFT JOIN posts p ON u.id = p.user_id LEFT JOIN likes l ON p.id = l.post_id GROUP BY u.id ORDER BY total_likes DESC;


6. Seleziona tutti i post degli utenti tra i 20 e i 30 anni (49)

SELECT p.* FROM posts p JOIN users u ON p.user_id = u.id WHERE TIMESTAMPDIFF(YEAR, u.birthdate, CURDATE()) BETWEEN 20 AND 30;

7. Seleziona il numero di post e di media per ogni utente (25)


BONUS
8. Seleziona tutti i post che contengono il tag 'serata' (8)
9. Ordina i post in base al numero di tag (165)
10. Ordina gli utenti in base al numero di tag usati nei loro post (25) -->