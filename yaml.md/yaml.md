- ### yaml files:
  - to store configuration data for software application
  - to store data that is to be interchanged with oher systems 
  - to store data that is to be used by s cript or program
- ### hash maps:
  - to store data that is accessed by key, such as a dict or lookup table
  - to store data that is to be used by a script or program

- ### 3 way: dict, list, list of dict
  - dict:  
      - Banana:
        - Calories: 105
          - Fact: 0.4g
          - Carbs: 27g
  - List:
      - Fruits:
        - Banana:
            Calories:105
            Fat: 0.4g
            Carbs: 27g
        - Grape:
            Calories: 62
            Fat: 0.4g
            Cars: 16g
  - List of dict:
    -   Color: Blue
        Model:
            Name: Corve
            Model: 1995
        Transmission: Manual
        Price: $2000
    -   Color: Gray
        Model:
            Name: Corvert
            Model: 2000
        Transmission: Automatic
        Price: $2000

- ### : Thứ tự thuộc tính không quan trọng 
        Banana:
            Caliories: 105
            Fat:104
Same****
        Orange:
            Fat:104
            Caliories:105
- ### : Thứ tự danh sách quan trọng     bash    - 
        Fruits:
            -banana
            -apple
 Not same ****       
        Fruits:
            -apple
            -banana