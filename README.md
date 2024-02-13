# C-Send-Email
        private void SendEmail(string toAddress)
        {
            try
            {
                string fromAddress = ""; // your gmail adress
                string password = ""; // First of all, you come to gmail account management, then you open two factor authentication, then you search for application passwords, for example "pptfjitqqqtvnewof" you will create such a password, we copy it here
                string toGmail = "";//recipient gmail 

                SmtpClient smtp = new SmtpClient
                {
                    Host = "smtp.gmail.com",
                    Port = 587,
                    EnableSsl = true,
                    DeliveryMethod = SmtpDeliveryMethod.Network,
                    UseDefaultCredentials = false,
                    Credentials = new NetworkCredential(fromAddress,toGmail,password)

                };

                MailMessage message = new MailMessage(fromAddress, toGmail)
                {
                    Subject = "", //you write what you want to write
                    Body = $": "
                };

                smtp.Send(message);


            }
            catch (Exception ex)
            {
                MessageBox.Show("There was an error sending an e-mail: " + ex.Message);
            }
        }
