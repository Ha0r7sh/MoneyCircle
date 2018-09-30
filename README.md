# MoneyCircle

final FirebaseUser user = mAuth.getCurrentUser() ;
user.sendEmailVerification()
    .addOnCompleteListener(this, new OnCompleteListener())
    {
      @Override
      
      public void onComplete(@NonNull Task task)
      {
        // Renewable Button
        
        findViewById(R.id.Verify_Email_Button).setEnabled(true);
        if(task.isSuccessful())
        {
          Toast.makeText(EmailPasswordActivity.this,"Verification Email Seent To "+ user.getEmail().Toast.LENGTH_SHORT).show();
        }
        
        else
        {
          Log.e(TAG,"SendEmailVerification",task.getException());
          Toast.makeText(EmailPasswordActivity.this,"Failed To Send Email verififcation",Toast.LENGTH_SHORT).show();
        }
    });
    
    mStatusTextView.setText(getString(R.String.EmailPassword_Status_fmt,user.getEmail(),user.isEmailVerified()));
