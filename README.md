# -*- coding: utf-8 -*-
# GitHub Profile | Odoo Developer

from odoo import models, fields, api


class OdooDeveloper(models.AbstractModel):
    _name = "profile.indeepa"
    _description = "Indeepa Wijesinghe – Odoo Developer"

    name = fields.Char(default="Indeepa Wijesinghe")
    role = fields.Char(default="Odoo Developer | Software Engineer")
    company = fields.Char(default="Cygnus One (Pvt) Ltd")
    location = fields.Char(default="Sri Lanka")
    education = fields.Char(default="BSc in Information Technology (Reading)")

    odoo_versions = fields.Selection(
        selection=[("16", "Odoo 16"), ("17", "Odoo 17"), ("18", "Odoo 18"), ("18", "Odoo 19")],
        string="Odoo Versions",
        default="18"
    )

    platforms = fields.Char(
        default="Community, Enterprise, Odoo.sh"
    )

    erp_domains = fields.Text(default="""
    -*
    """)

    technical_skills = fields.Text(default="""
    - Python (ORM, Models, Wizards)
    - XML (Form, Tree, Kanban Views)
    - OWL JS (POS & Dashboard UI)
    - Security (Groups, Access Rights, Record Rules)
    - Accounting & Inventory Integrations
    """)

    responsibilities = fields.Text(default="""
    - Requirement gathering & functional consulting
    - Client communication & solution design
    - Training and mentoring intern software engineers
    """)

    @api.model
    def profile_summary(self):
        return f"""
        👋 {self.name}
        💼 {self.role}
        🏢 {self.company}
        📍 {self.location}

        Odoo Versions: 16 | 17 | 18 | 19
        Platforms: {self.platforms}
        """



if __name__ == "__main__":
    developer = OdooDeveloper()
    print(developer.profile_summary())
