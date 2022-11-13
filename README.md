
# Steganography using LSB technique

 Steganography is the technique of hiding secret data within an ordinary non-secret file or message in order to avoid detection. The secret data is then extracted at its destination. Image steganography is performed for images and the concerning data is also decrypted to retrieve the message image. Since this can be done in several ways, image steganography is studied and one of the methods is used to demonstrate it. Image steganography refers to hiding information i.e., text, images or audio files in another image or video files. Image Steganography is a process by which hidden and secure messages are added to images, often in such a way that the messages can’t be extracted unless you know their location. Image steganography can either be used for storage or communication. 


## Deployment

You will need to install PIL and opencv to run the project 

```bash
  pip install Pillow
```

```bash
  pip install opencv-python
```
## Implementation

Each pixel’s R G B values have 8 bits. 
In our cover image, for each pixel, for each of its red, green and blue values,
we are using 4 of these bits to hide information. 
Since we are putting information about the hidden text in the bits,
we will lose the data about the cover image in those bits.

-   Say we have a pixel 
    ![image](https://user-images.githubusercontent.com/97322648/201515242-1e6324e3-373e-4423-b78f-3c3c0ae97007.png)

-    So when a pixel has the RGB values (255,255,255), to the computer that’s (1111 1111, 1111 1111, 1111 1111).


     ![image](https://user-images.githubusercontent.com/97322648/201515268-5ce6e5dc-8c57-4545-9c92-55cc6d75a19e.png)

-   Each red, green and blue value has 8 binary digits, called bits. The smallest number represented in 8 bits is 0 and the largest is 1111 1111, which is 255 in base 10.


- A pixel with a red value of 240 looks like this:

  ![image](https://user-images.githubusercontent.com/97322648/201515330-8becb474-a31b-4a4e-8c10-cf0edd6f1f31.png)

-  Now, consider changing the rightmost 4 bits to end up with 1111 1111, or 255 in decimal. We have changed the original value by 15 and it looks like this:

   ![image](https://user-images.githubusercontent.com/97322648/201515354-9bf379d0-d74c-4cc2-8de5-401b6274a636.png)

   NOT TOO DIFFERENT FROM FIRST COLOR
-  If these values are changed, the pixel value maybe changed up to 240. The rightmost 4 bits are the least important. 
-  If these bits are changed, the most you could change the value by is 15. 
-  Therefore, we are leaving the leftmost bits and use the rightmost 4 bits to hide our secret data in. this way our cover image wont change too much. 

## ENCRYPTION

- Run the encryption code block 

  ![Screenshot 2022-11-13 151222](https://user-images.githubusercontent.com/97322648/201515738-fa8c8e3d-e8cc-46e9-8e22-a707d586d8c6.jpg)

- Click on choose Image and select an image from your local storage

  ![Screenshot 2022-11-13 151308](https://user-images.githubusercontent.com/97322648/201515786-007ce073-4e10-4942-b532-c5f3ccdf2dd2.jpg)

- Write a secret text and Click "Encode" 
  
  ![Screenshot 2022-11-13 151322](https://user-images.githubusercontent.com/97322648/201515831-4553d1d5-8378-457f-9f97-b90b3d039adf.jpg)

-  Your image is encoded with the secret text and the new stego image is saved as "encrypted_image.png" at the root directory of your code.




## DECRYPTION



- Click on "Start Program".

  It reads the encryped_image.png and decrypes for the secret message

  ![Screenshot 2022-11-13 151342](https://user-images.githubusercontent.com/97322648/201515972-8ec5e9fb-b187-46e8-9f4c-257fd9dfccd6.jpg)

- You have successfully retrieved the secret text.
   ![Screenshot 2022-11-13 151357](https://user-images.githubusercontent.com/97322648/201516038-f9972711-a4d5-48c9-87c9-274c2f709f70.jpg)
