# Android-Custom-Dialog
All kinds of custom dialog

## Usage

###### This dialog has one EditText and two Button.

1. Add activity

```
Dialog dialog = new Dialog(MainActivity.this);
       dialog.setContentView(R.layout.category_add_new_dialog);
       dialog.getWindow().setLayout(ActionBar.LayoutParams.MATCH_PARENT, ActionBar.LayoutParams.WRAP_CONTENT);
       dialog.setCancelable(false);
       dialog.getWindow().setBackgroundDrawable(new ColorDrawable(Color.TRANSPARENT));
       dialog.show();

       Button cancelButton = (Button) dialog.findViewById(R.id.btn_cancel);
       EditText editText=dialog.findViewById(R.id.et_dialog);

       cancelButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {      
                dialog.dismiss();
            }
        });

        Button okButton = (Button) dialog.findViewById(R.id.btn_ok);
        okButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
     
                if(TextUtils.isEmpty(editText.getText())){
                    Toast.makeText(MainActivity.this, "Please type ...!", Toast.LENGTH_SHORT).show();
                    
                }else {
                   
                    dialog.dismiss();
                }

            }
        });
```

2. Add layout

```
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:layout_margin="20dp"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    android:background="@drawable/dialog_bg"
    android:orientation="vertical">


    <LinearLayout
        android:layout_margin="10dp"
        android:gravity="center"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:orientation="horizontal">

        <ImageView
            android:layout_marginRight="10dp"
            android:layout_width="50dp"
            android:layout_height="50dp"
            android:src="@mipmap/ic_launcher" />

        <TextView
            android:layout_marginLeft="10dp"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_gravity="center"
            android:text="New Category"
            android:textAlignment="center"
            android:textColor="#000"
            android:textSize="20sp"
            android:textStyle="bold" />

    </LinearLayout>



    <EditText
        android:id="@+id/et_dialog"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_gravity="center"
        android:layout_marginLeft="10dp"
        android:layout_marginRight="10dp"
        android:hint="Enter Category"
        android:padding="10dp"
        android:inputType="textPersonName"
        android:textAlignment="center"
        android:textColor="#000000"
        android:background="@drawable/edittext_bg"
        android:textSize="20sp" />



    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_margin="10dp"
        android:gravity="center"
        android:orientation="horizontal">


        <com.google.android.material.button.MaterialButton
            android:id="@+id/btn_ok"
            app:backgroundTint="@color/amber_A700"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_margin="10dp"
            android:text="OK" />



        <com.google.android.material.button.MaterialButton
            android:id="@+id/btn_cancel"
            android:backgroundTint="@color/amber_A700"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_margin="10dp"
            android:textAllCaps="false"
            android:text="Cancel" />
    </LinearLayout>
</LinearLayout>

```

3. Add drawable

```
///name dialog_bg

<?xml version="1.0" encoding="utf-8"?>
<shape xmlns:android="http://schemas.android.com/apk/res/android">
    <solid android:color="#eeffffff"/>
    <stroke android:width="2dp" android:color="@color/yellow_A700" />
    <corners android:radius="20dp"/>
    <padding android:left="0dp" android:top="0dp" android:right="0dp" android:bottom="0dp" />
</shape>

/// name edittext_bg

<?xml version="1.0" encoding="utf-8"?>
<shape xmlns:android="http://schemas.android.com/apk/res/android">
    <solid android:color="@color/grey_200"/>
    <stroke android:width="2dp" android:color="@color/yellow_A700" />
    <corners android:radius="5dp"/>
    <padding android:left="0dp" android:top="0dp" android:right="0dp" android:bottom="0dp" />
</shape>
```

###### This dialog has one TextView and three Button.

1. Add activity

```
Dialog dialog = new Dialog(MainActivity.this);
       dialog.setContentView(R.layout.category_edit_dialog);
       dialog.getWindow().setLayout(ActionBar.LayoutParams.MATCH_PARENT, ActionBar.LayoutParams.WRAP_CONTENT);
       dialog.setCancelable(false);
       dialog.getWindow().setBackgroundDrawable(new ColorDrawable(Color.TRANSPARENT));
       dialog.show();

       Button updatebtn=dialog.findViewById(R.id.edit_dialog_update_btn);
       Button deletebtn=dialog.findViewById(R.id.edit_dialog_delete_btn);
       Button cancelbtn=dialog.findViewById(R.id.edit_dialog_cancle_btn);

        updatebtn.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                
                dialog.dismiss();
            }
        });

        deletebtn.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                
                dialog.dismiss();
            }
        });

        cancelbtn.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                dialog.dismiss();
            }
        });
```

2. Add layout

```
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:layout_margin="20dp"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    android:background="@drawable/dialog_bg"
    android:orientation="vertical">


    <LinearLayout
        android:layout_margin="10dp"
        android:gravity="center"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:orientation="horizontal">

        <ImageView
            android:layout_marginRight="10dp"
            android:layout_width="50dp"
            android:layout_height="50dp"
            android:src="@mipmap/ic_launcher" />

        <TextView
            android:layout_marginLeft="10dp"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_gravity="center"
            android:text="Edit Category"
            android:textAlignment="center"
            android:textColor="#000"
            android:textSize="20sp"
            android:textStyle="bold" />

    </LinearLayout>

    <TextView
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:padding="5dp"
        android:layout_margin="10dp"
        android:text="Select make your function."
        android:textColor="@color/black"/>

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_margin="5dp"
        android:gravity="center"
        android:orientation="horizontal">


        <com.google.android.material.button.MaterialButton
            android:id="@+id/edit_dialog_update_btn"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_margin="5dp"
            android:text="Update"
            android:textAllCaps="false"
            app:backgroundTint="@color/amber_A700" />


        <com.google.android.material.button.MaterialButton
            android:id="@+id/edit_dialog_delete_btn"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_margin="5dp"
            android:backgroundTint="@color/amber_A700"
            android:text="Delete"
            android:textAllCaps="false" />

        <com.google.android.material.button.MaterialButton
            android:id="@+id/edit_dialog_cancle_btn"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_margin="5dp"
            android:backgroundTint="@color/amber_A700"
            android:text="Cancel"
            android:textAllCaps="false" />
    </LinearLayout>
</LinearLayout>
```

###### This dialog has one ScrollView and two Button.Add select your Editext in ScrollView and you can change data.

1. Add activity

```
 Dialog dialog = new Dialog(CategorySelectActivity.this);
// Include dialog.xml file
        dialog.setContentView(R.layout.category_update_dialog);
        dialog.getWindow().setLayout(ActionBar.LayoutParams.MATCH_PARENT, ActionBar.LayoutParams.WRAP_CONTENT);
        dialog.setCancelable(false);
        dialog.getWindow().setBackgroundDrawable(new ColorDrawable(Color.TRANSPARENT));
        dialog.show();

        LinearLayout linearLayout=dialog.findViewById(R.id.update_dialog_ll);
        Button okbtn=dialog.findViewById(R.id.btn_ok);
        Button cancelbtn=dialog.findViewById(R.id.btn_cancel);
        
        /// show item array in ScrollView

        for(int i=0;i<setCategoryList.size();i++){
            Drawable drawable = getResources().getDrawable( R.drawable.edittext_bg );
            EditText editText=new EditText(this);
            editText.setText(setCategoryList.get(i));
            editText.setTextColor(Color.parseColor("#000000"));
            editText.setBackground(drawable);
            editText.setPadding(10,10,10,10);
            LinearLayout.LayoutParams layoutParams=new LinearLayout.LayoutParams(LinearLayout.LayoutParams.MATCH_PARENT,
                    LinearLayout.LayoutParams.WRAP_CONTENT);

            layoutParams.setMargins(5,5,5,5);

            linearLayout.addView(editText,layoutParams);

        }
        
        /// show item array in ScrollView

        okbtn.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
            
                ///get value from ScrollView item
                int etcount=linearLayout.getChildCount();

                for(int j=0;j<etcount;j++){
                    EditText editText=(EditText)linearLayout.getChildAt(j);
                    Log.d("editTexteditText",editText.getText().toString());
                    Log.d("editTexteditText",setCategoryListID.get(j));
                   
                }
                
                ///get value from ScrollView item
                dialog.dismiss();
            }
        });
        cancelbtn.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                dialog.dismiss();
            }
        });
```

2. Add layout

```
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:layout_margin="20dp"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    android:background="@drawable/dialog_bg"
    android:orientation="vertical">


    <LinearLayout
        android:layout_margin="10dp"
        android:gravity="center"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:orientation="horizontal">

        <ImageView
            android:layout_marginRight="10dp"
            android:layout_width="50dp"
            android:layout_height="50dp"
            android:src="@mipmap/ic_launcher" />

        <TextView
            android:layout_marginLeft="10dp"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_gravity="center"
            android:text="Update Category"
            android:textAlignment="center"
            android:textColor="#000"
            android:textSize="20sp"
            android:textStyle="bold" />

    </LinearLayout>


    <ScrollView
        android:layout_width="match_parent"
        android:layout_margin="10dp"
        android:layout_height="250dp">
        <LinearLayout
            android:id="@+id/update_dialog_ll"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:orientation="vertical">

        </LinearLayout>

    </ScrollView>
    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_margin="5dp"
        android:gravity="center"
        android:orientation="horizontal">


        <com.google.android.material.button.MaterialButton
            android:id="@+id/btn_ok"
            app:backgroundTint="@color/amber_A700"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_margin="10dp"
            android:text="OK" />



        <com.google.android.material.button.MaterialButton
            android:id="@+id/btn_cancel"
            android:backgroundTint="@color/amber_A700"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_margin="10dp"
            android:textAllCaps="false"
            android:text="Cancel" />
    </LinearLayout>
</LinearLayout>
```

###### This dialog has one RecyclerView and two Button.Add select your TextView in RecyclerView.

1. Add activity

```
Dialog dialog = new Dialog(CategorySelectActivity.this);
// Include dialog.xml file
        dialog.setContentView(R.layout.category_delete_dialog);
        dialog.getWindow().setLayout(ActionBar.LayoutParams.MATCH_PARENT, ActionBar.LayoutParams.WRAP_CONTENT);
        dialog.setCancelable(false);
        dialog.getWindow().setBackgroundDrawable(new ColorDrawable(Color.TRANSPARENT));
        dialog.show();

        RecyclerView recyclerView_dialog=dialog.findViewById(R.id.category_recycler_view);
        Button yesbtn=dialog.findViewById(R.id.btn_yes);
        Button nobtn=dialog.findViewById(R.id.btn_no);

        LinearLayoutManager linearLayoutManager=new LinearLayoutManager(this);
        categorySelectAdapter=new RVCategorySelectAdapter(CategorySelectActivity.this,setCategoryListID,setCategoryList);
        recyclerView_dialog.setLayoutManager(linearLayoutManager);
        recyclerView_dialog.setAdapter(categorySelectAdapter );

        yesbtn.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {

                for(int j=0;j<setCategoryListID.size();j++){
                   
                }  
                dialog.dismiss();
            }
        });

        nobtn.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                dialog.dismiss();
            }
        });

```

2. Add layout

```
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:layout_margin="20dp"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    android:background="@drawable/dialog_bg"
    android:orientation="vertical">


    <LinearLayout

        android:layout_margin="10dp"
        android:gravity="center"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:orientation="horizontal">

        <ImageView
            android:layout_marginRight="10dp"
            android:layout_width="50dp"
            android:layout_height="50dp"
            android:src="@mipmap/ic_launcher" />

        <TextView
            android:layout_marginLeft="10dp"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_gravity="center"
            android:text="Delete Category"
            android:textAlignment="center"
            android:textColor="#000"
            android:textSize="20sp"
            android:textStyle="bold" />

    </LinearLayout>


    <androidx.recyclerview.widget.RecyclerView
        android:layout_margin="10dp"
        android:id="@+id/category_recycler_view"
        android:layout_width="match_parent"
        android:layout_height="250dp"
        app:layout_constraintBottom_toTopOf="@+id/category_next_btn"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/category_ll" />



    <LinearLayout

        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_margin="10dp"
        android:gravity="center"
        android:orientation="horizontal">


        <com.google.android.material.button.MaterialButton
            android:id="@+id/btn_yes"
            app:backgroundTint="@color/amber_A700"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_margin="10dp"
            android:text="Yes" />


        <com.google.android.material.button.MaterialButton
            android:id="@+id/btn_no"
            android:backgroundTint="@color/amber_A700"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_margin="10dp"
            android:textAllCaps="false"
            android:text="No" />
    </LinearLayout>
</LinearLayout>
```
